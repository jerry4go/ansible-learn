# 1.在centos安装

yum install -y epel-release

yum install -y ansible

验证安装的版本

ansible --version

```
ansible 2.8.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = [u'/root/.ansible/plugins/modules', u'/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python2.7/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 2.7.5 (default, Oct 30 2018, 23:45:53) [GCC 4.8.5 20150623 (Red Hat 4.8.5-36)]

```

# 2.配置node主机IP

vim /etc/ansible/hosts

# 3.常用命令

ping所有的节点是否能正常通讯

ansible -m ping all

查看指定服务器的内存大小

ansible -m shell -a 'free -m' host1

