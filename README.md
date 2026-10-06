# 1 脚本说明
脚本用于定时对比被备份目录与完全备份的目录文件的差异，并将差异的文件按时间创建目录保存。
差异文件保存目录如下，
~~~
# tree -L 1 /backup/nextcloudBackup/monthlyDiffBackup
/backup/nextcloudBackup/monthlyDiffBackup
├── 2026-08-28
├── 2026-08-29
├── 2026-08-30
├── 2026-08-31
├── 2026-09-01
├── 2026-09-02
├── 2026-09-03
├── 2026-09-04
├── 2026-09-05
├── 2026-09-06
├── 2026-09-07
├── 2026-09-08
├── 2026-09-09
├── 2026-09-10
├── 2026-09-11
├── 2026-09-12
├── 2026-09-13
├── 2026-09-14
├── 2026-09-15
├── 2026-09-16
├── 2026-09-17
├── 2026-09-18
├── 2026-09-19
├── 2026-09-20
├── 2026-09-21
├── 2026-09-22
├── 2026-09-23
├── 2026-09-24
├── 2026-09-25
~~~
# 2 使用方法
# 2.1 部署脚本
~~~
# wget -O fileBackupTool.sh https://github.com/tanzhenchao/fileBackupTool/blob/main/fileBackupTool
# cp fileBackupTool.sh /usr/local/bin/fileBackupTool
# chmod +x /usr/local/bin/fileBackupTool
~~~

# 2.2 修改脚本配置
~~~
# vim /usr/local/bin/fileBackupTool
~~~
根据实际情况修改下面的参数
~~~
fileDir="/data/nextcloud-data"
backupDir="/backup/nextcloudBackup"
diffBackupKeeptime="+180"
~~~
- 参数“fileDir”定义需要备份的文件所在目录
- 参数“backupDir”定义备份文件的存储目录
- 参数“diffBackupKeeptime”定义备份文件保存的天数

# 2.3 获取帮助
~~~
# fileBackupTool
~~~
可见如下显示，
~~~
Usage: /usr/local/bin/fileBackupTool {monthlyFullBackup|monthlyDiffBackup}
~~~

# 2.4 执行全备份
~~~
# fileBackupTool monthlyFullBackup
~~~

# 2.5 执行差异备份
~~~
# fileBackupTool monthlyDiffBackup
~~~
