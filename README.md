```shell
ssh-keygen	# 创建公钥私钥对
ssh -p <port> <user>@<host> <cmd>	# 连接后执行命令并断开
sudo service ssh restart	# 重启SSH服务
sudo vim /etc/ssh/sshd_config	# 修改port
```

```shell
# client: ~/.ssh/config
Host <host_alias>
  HostName <host>
  User hty
  Port 2222
Host *
  ServerAliveInterval 120	# 超时时间
  StrictHostKeyChecking no	# 自动讲新主机加入known_hosts
  UserKnownHostsFile /dev/null	# 取消warn
```

```shell
# server: /etc/ssh/sshd_config
Port 2222	# 修改port
PasswordAuthentication no	# 禁用密码连接
AllowUsers *	# 允许访问的用户
AllowGroups *	# 允许访问的用户组
PermitRootLogin no	# root才能访问
```





