#my vim configuration with pathogen to manage bundles
=====================================================
This vim configuration uses pathogen to manage bundles. As we know, if we use git clone to download plugin bundles, in fact, each bundle is a git repository. So we need to use git submodule command  to update the configuration. <\br>
This configuration contains following plugin:
        surptab.vim \\use tab to autocomplete
        fortran.vim \\fortran smart indent
        solarized.vim \\use fancy solarized color in vim
        fugitive.vim 
## How to configure you PC the first time you use git —写在前面－初次使用git 如何配置终端
生成配对的公钥和私钥

        mkdir .ssh && cd .ssh    终端新建个 .ssh文件目录并进入到该目录          
        ssh-Keygen -t rsa -C "your_email@example.com"     后面“ ”里面 随意输入个邮箱就行,回车会提示你输入密码什么的，可以无视一直回车下去。  
        ls -la    查看是否存在 id\_rsa(私钥) id\_rsa.pub(公钥) 这两个东西，如果存在就成功了
        pbcopy < ~/.ssh/id_rsa.pub     拷贝 公钥内容到剪切版
        
登陆github，选择Account Settings-->SSH Keys 添加ssh
Title：xxxxx@gmail.com
Key：打开你生成的id\_rsa.pub文件，将其中内容拷贝至此。

完成以上步骤，就可以在个人终端上往github 的repositories （俗称仓库）里上传啦

## 在终端新建工作区并上传到github 仓库 
        
        touch README    新建一个记录提交操作的文档
        git init    初始化本地仓库
        git add README.md    加入README.md文件
        git add .    加入该工作区下所有文件（整个项目）
        git status    检查状态 如果都是绿的 证明成功
        git commit -m "first commit"    提交到要地仓库，并写一些注释
        git remote add origin git@github.com:excellenthua/Vimconfig.git
        \\连接远程仓库并建了一个名叫：origin的别名;?  初次设置的时候需要执行该命令，之后就不需要了。
        git push -u origin master       
     将本地仓库的东西提交到地址是origin的地址，master分支下，之后直接输入git push 命令好像就可以了
        git pull     从远程服务器下载
## How to use submodule to download plugins (For myself)
以插件vim-colors-solarized为例

        cd ~/.vim
        mkdir ~/.vim/bundle
        git submodule add http://github.com/altercation/vim-colors-solarized.git bundle/vim-colors-solarized
        git add .
        git commit -m "Install vim-colors-solarized bundle as a submodule."
        git push
## How to install this vim configuration (For users)

        cd ~  
        git clone http://github.com/excellenthua/Vimconfig.git ~/.vim  \\git clone this vim configuration to ~/.vim directoty
        ln -s ~/.vim/vimrc ~/.vimrc  \\symbolic link .vimrc file
        cd ~/.vim 
        git pull  \\download from github
        git submodule init  \\init submodule
        git submodule update  \\update submodule,always use this command can keep you vim configuration consisitent with the latest version
        
