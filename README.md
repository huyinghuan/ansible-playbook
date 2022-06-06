## ansible 部署

必备的内置playbook

```shell
ansible-galaxy collection install community.general
```

### 运行指定tags

```
ansible-playbook init.playbook.yml --tags init
```

### 提权

```
-K, --ask-become-pass: ask for privilege escalation password
```

### 指定变量文件

```
# 指定变量文件
ansible-playbook init.playbook.yml --tags init -e "@var.json"
# 或者手动指定变量名
# ansible-playbook init.playbook.yaml --tags golang -e "host=nft-for"
# 当然，也可以在 yml 里面通过 var_files 指定
```


### 路径

yml里面配置里的本地相对路径是相对于 yml 文件所在目录的。而不是 `ansible-playbook`的运行时目录。
即

```
cd /root
ansible-playbook xxx/xxx/init.playbook.yml --tags init

那么 init.playbook.yml 里面引入的本地相对路径是相对于 `/root/xxx/xxx`,而不是 `root`
```




### 安装clash

本地使用 `pm2` 管理
```
ansible-playbook softerware/clash/clash.yml --skip-tags docker
```

