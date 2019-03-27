## pm2 - node.js进程管理和监控分析
1.pm2 简介  
2.pm2 命令使用  
3.pm2 编程接口  
4.pm2 monit  
5.pm2 原理简析  
6.其他

## pm2 简介 
pm2 是一个具有内置负载均衡器 用于Node.js应用在生产环境的进程管理器。 它可以让应用程序保持活跃，无需停机即可重新加载它们。  
pm2 特性  
日志管理：应用程序日志保存在服务器的硬盘中~/.pm2/logs/  
负载均衡：PM2可以通过创建共享同一服务器端口的多个子进程来扩展您的应用程序。这样做还允许您以零秒停机时间重新启动应用程序。  
终端监控：可以在终端中监控您的应用程序并检查应用程序运行状况（CPU使用率，使用的内存，请求/分钟等）。  
静态服务：支持静态服务器功能  
多平台支持：适用于Linux，macOS，Windows  

## pm2 命令使用
pm2 start app.js  最简单的启用一个应用:  
pm2 stop app_name|app_id    
pm2 delete app_name|app_id  
pm2 restart app_name|app_id  
pm2 stop all  停止所有应用  
pm2 list  查看所有的进程  
pm2 status  同 pm2 list  
pm2 describe app_name|app_id  查看某一个进程的信息  
pm2 save    保存当前应用列表  
pm2 resurrect  重新加载保存的应用列表  

## pm2 编程接口
http://pm2.keymetrics.io/docs/usage/pm2-api/  
pm2.connect 和正在运行的pm2 守护进程建立连接，如果没有会先创建然后建立连接。  
pm2.start 启动一个脚本，会有很多的配置选项  
pm2.disconnect 和pm2 守护进程断开连接  
pm2.stop 停掉一个进程，但是会保留在pm2的列表里  
pm2.restart  
pm2.delete 停掉一个进程，并且从pm2的列表里移除  
pm2.reload 集群模式下不宕机重启，至少保留一个进程是运行的。  
pm2.gracefulReload reload前会向进程发送一个关闭消息  
pm2.killDaemon 杀死pm2 守护进程  
pm2.describe(process,errback)  返回一个pm2管理的进程的相关信息  
pm2.list(errback) 获取pm2 管理的所有的进程的列表，能获取一个包含上面信息的列表。  
pm2.dump 将进程列表以json 格式输出到文件  
pm2.flush 清空日志  
pm2.launchBus 打开一个message bus.  
pm2.sendSignalToProcessName 向指定process 发送信号  
pm2.startup 开机启动脚本  
pm2.sendDataToProcessId 向进程发送消息。  

## pm2 编程接口


