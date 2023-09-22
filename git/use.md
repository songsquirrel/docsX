## git连接远程仓库初始化配置
```shell
# config user name 
git config --global user.name "${yourName}"
# config email
git config --global user.email "${yourEmail}"
# generate ssh-rsa
ssh-keygen -t rsa -C "walker@395135385@qq.com"
# according info to config your ssh-key
```
## git常用操作
```shell
# 查看当前待提交的content
git status
# 清除当前文件夹待提交的内容, 重新add
git rm -r --cached .
# 添加修改内容至待提交区
git add .
# 提交 
git commit -m "message"
# git push <远程主机名> <本地分支名>:<远程分支名>
git push origin master
```