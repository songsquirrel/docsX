### how to push code to github by github cli 

the important point to use github cli for me is it could authenticate to Git.

1. [安装见官网](https://github.com/cli/cli#installation)
2. 登录
   ```shell
   gh login auth
   ```
3. 克隆仓库/创建新仓库
   ```shell
   gh repo clone
   gh repo create
   ```
4. 其余git操作同样可以使用.github cli授权认证信息给git. 可通过指定hostname来指定作用gitlab站.


[官网手册](https://cli.github.com/manual/)
   