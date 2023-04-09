# Git-on-Linux

## 在Linux上安装git(以Ubuntu为例)
`sudo apt-get install git`

## 第一次使用git
1. 本地创建SSH

`ssh-keygen -t rsa -C 你的邮箱`

2. 成功的话会在~/下生成.ssh隐藏文件夹,ctrl+h可以显示隐藏文件夹
3. github上创建SSH，Account Setting->New SSH Key->title(随便写)->Key(将id_rsa.pub中的内容复制进去即可)
4. 验证是否成功

`ssh -T git@github.com`

出现You've successfully authenticated, but GitHub does not provide shell access.说明成功连上github

5. 设置username和email

`git config --global user.name 你的github名称`

`git config --global user.email 你的邮箱`

6. 创建一个github远程仓库
先创建一个github远程仓库:右上角点击头像->Your Repositories->New
![成电飞书20230409-162508](https://user-images.githubusercontent.com/90328028/230762401-f68697d7-86b3-490e-a030-8482af1157b0.png)

填写你的仓库名(Repository name)，使用英文填写

Desription根据自己的需要填写

选择Public or Private是否向他人公开你的仓库

Add a README file(推荐添加一个readme文件)

7. 在本地提交代码

`git init`

初始化项目

`git add .`

将你的文件添加到暂存区(git add .添加所有可追踪文件，git add + 文件名 添加指定文件， git add -f + 文件名 强制添加文件，可追踪文件和不可追踪文件均可，不可追踪文件通过git add添加后可以通过git追踪到)

`git commit -m 你对文件的描述`

`git remote add origin + 仓库地址`

仓库地址获取:打开你的仓库->Code->SSH(推荐SSH地址)

`git push origin main`

将文件推送到main分支
