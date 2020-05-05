- 绑定github账号
  - 生成key: ssh-keygn -t rsa -C "baizhen9406@163.com";一直回车即可
  - 复制id_rsa.pub中内容到github账号setting->SSH and GPG keys->SSH keys->New SSH keys中,保存即可
  - 验证是否绑定成功: ssh -T git@github.com
  - 设定username和email: 1. git config --global user.name "Thomas-Lee"; 2. git config --global user.email "baizhen9406@163.com"

- 开始写项目
  - 初始化: git init
  - 将所有文件添加到仓库: git add .
  - 建立远程连接(增添更新源): git remote add origin git@github.com:YourThomasLee/NLPer-Interview.git
  - 拉取代码: git pull git@github.com:YourThomaLee/NLPer-Interview.git
  - 把本地代码传到github上
    - 增加所有文件到cache中: git add .
    - 提交cache中的文件到仓库: git commit -m "first commit"
    - 提交到githb上: git push git@github.com:YourThomasLee/NLPer-Interview.git; git push -u origin master
    - 代码合并: git pull -rebase origin master
  - 更新: 简单粗暴的将所有已经跟踪文件的更新同步到库中 git commit -am "message" 
  
- 问题: The file will have its original line endings in your working directory

  原因: 从别人github地址上通过git clone下载下来，而又想git push到自己的github上，那么就会出现上面提示的错误信息

  执行以下代码:

  ```bash
  git rm -r --cached .
  git config core.autocrlf false
  git add .
  ```

- 问题: Please make sure you have the correct access rights and the repository exists

  1.可能ssh key出现问题: ssh -T git@github.com检查

  2.可能配置文件出现问题: cat .git/config, 出现问题修改下就可以

