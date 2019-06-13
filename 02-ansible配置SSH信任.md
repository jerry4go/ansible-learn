1.配置忽略主机指纹校验，不会提示你要输入yes
```
vim /etc/ansible/ansible.cfg

[defaults]
host_key_checking = false
```
如果不想修改配置文件，一次性配置变量
```
export ANSIBLE_HOST_KEY_CHECKING=False
```

2.拷贝本地的公钥到远程主机
```
ansible -m authorized_key -a "user=root key='{{ lookup('file','/root/.ssh/id_rsa.pub') }}'" -k server
```

3.