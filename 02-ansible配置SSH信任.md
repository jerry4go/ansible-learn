1.配置忽略主机指纹校验，不会提示你要输入yes

vim /etc/ansible/ansible.cfg

[defaults]
host_key_checking = false

2.拷贝本地的公钥到远程主机
```
ansible -m authorized_key -a "user=root key='{{ lookup('file','/root/.ssh/id_rsa.pub') }}'" -k server
```

3.