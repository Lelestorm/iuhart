# Nginx Error
###### kevent() reported that connect() failed (61: Connection refused)
原因：php-fmt未启动
解决：sudo php-fmt（启动php-fmt）
###### Nginx日志目录：usr/local/var/log/nginx/error.log | usr/local/var/log/nginx/access.log
###### php-fmt日志:usr/local/var/log/php-fmt.log
###### Nginx: stat() failed (13: permission denied)
FastCGI sent in stderr: "Primary script unknown" while reading response header from upstream
