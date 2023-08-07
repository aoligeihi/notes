### 设置git user和email
`$ git config --global user.name "lisi"`
`$ git config --global user.email "lisi@gmail.com"`
### 生成ssh
`cd ~/.ssh` 查看是否已经有ssh
`$ ssh-keygen -t rsa -C "lisi@gmail.com"` 生成ssh密钥
