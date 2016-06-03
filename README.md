<snippet>
  <content><![CDATA[
# ${1:  my vim configuration }

=====================================================
## 写在前面－如何通过git上传到仓库

'mkdir .ssh && cd .ssh' //终端新建个 .ssh文件目录并进入到该目录
'ssh-Keygen -t rsa -C "your_email@example.com"' //后面“ ”里面 随意输入个邮箱就行,回车会提示你输入密码什么的，可以无视一直回车下去。
'ls -la' // 查看是否存在 id_rsa(私钥) id_rsa.pub(公钥) 这两个东西，如果存在就成功了
'pbcopy < ~/.ssh/id_rsa.pub' //拷贝 公钥内容到剪切版
登陆github，选择Account Settings-->SSH Keys 添加ssh
Title：xxxxx@gmail.com
Key：打开你生成的id_rsa.pub文件，将其中内容拷贝至此。

'touch README' //新建一个记录提交操作的文档
'git init' //初始化本地仓库
'git add README.md' //添加
'git add .' //加入所有项目
'git status' //检查状态 如果都是绿的 证明成功
'git commit -m "first commit"'//提交到要地仓库，并写一些注释
'git remote add origin git@github.com:excellenthua/Vimconfig.git' //连接远程仓库并建了一个名叫：origin的别名;?初次设置的时候需要执行该命令，之后就不需要了。
'git push -u origin master' //将本地仓库的东西提交到地址是origin的地址，master分支下，之后直接输入git push 命令好像就可以了
'git pull' \\从远程服务器下载
=====================================================
## 如何采用submodule方式更新插件

以插件vim-colors-solarized为例
'cd ~/.vim
mkdir ~/.vim/bundle
git submodule add http://github.com/altercation/vim-colors-solarized.git bundle/vim-colors-solarized
git add .
git commit -m "Install vim-colors-solarized bundle as a submodule."
git push'
=====================================================
## 如何安装并使用

'cd ~
git clone http://github.com/username/dotvim.git ~/.vim
ln -s ~/.vim/vimrc ~/.vimrc
ln -s ~/.vim/gvimrc ~/.gvimrc
cd ~/.vim
git pull
git submodule init
git submodule update'

]]></content>
  <tabTrigger>readme</tabTrigger>
  </snippet>
