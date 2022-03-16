## ansible 部署

必备的内置playbook

```shell
ansible-galaxy collection install community.general
```

## 安装指定tags

```
ansible-playbook init.playbook.yml --tags init -e "@var.json"
```

## 提权

```
-K, --ask-become-pass: ask for privilege escalation password
```