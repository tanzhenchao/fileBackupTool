# 1 脚本说明
脚本用于定时对比文件的差异并将差异文件按时间保存到特定目录。

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
logFile="/var/log/fileBackup.log"
lockFullBackupFile="/var/run/fullbackup.lock"
lockDiffBackupFile="/var/run/diffbackup.lock"
diffBackupKeeptime="+180"
~~~

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
