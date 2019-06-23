# ansible 主要参数

-u username     

指定SSH连接的用户名，即执行后面命令的用户

-i inventory_file 

指定所使用的inventory文件的位置，默认为/etc/ansible/hosts

-m module    

指定使用的模块，默认为command,常见的模块有command,shell,script,yum,copy等

-f  10       

指定并发数，并发量大的时候，提高该值

--sudo [-k]  

当需要root权限执行的话，-k参数用来输入root密码

-a           

指定模块的参数，可以是命令等

# 基本命令

ping命令

`ansible all -a 'ping baidu.com -c 1'`

正则表达式

`ansible 192.168.33.*  -m command -a "df -h"`

文件拷贝

`ansible all -m copy -a 'src=/etc/passwd dest=/tmp/ mode=755 owner=root'`

目录拷贝

`ansible all -m copy -a 'src=/root/nginx dest=/tmp/ mode=755 owner=root'`

yum安装

`ansible all -m yum -a "name=ntpdate,telnet state=installed"`


# ansible模块文档查看

查看yum模块如何使用

`ansible-doc yum`

`ansible-doc -s yum`

列出当前ansible支持的所有模块

`ansible-doc -l`



























