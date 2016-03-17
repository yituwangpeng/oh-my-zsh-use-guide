#oh my zsh使用指南
##Overview
Shell是Linux/Unix的一个外壳，它负责外界与Linux内核的交互，接收用户或其他应用程序的命令，然后把这些命令转化成内核能理解的语言，传给内核，内核是真正干活的，干完之后再把结果返回用户或应用程序。Linux/Unix提供了很多种Shell，常用的Shell有这么几种，sh、bash、csh等，想知道你的系统有几种shell，可以通过以下命令查看：
    cat /etc/shells 
###结果输出如下：
    /bin/bash
    /bin/csh
    /bin/ksh
    /bin/sh
    /bin/tcsh
    /bin/zsh   
在 Linux 里执行这个命令和 Mac 略有不同，你会发现 Mac 多了一个 zsh，也就是说 OS X 系统预装了个 zsh，这是个神马 Shell 呢？目前常用的 Linux 系统和 OS X 系统的默认 Shell 都是 bash，但是真正强大的 Shell 是深藏不露的 zsh， 这货绝对是马车中的跑车，跑车中的飞行车，史称『终极 Shell』，但是由于配置过于复杂，所以初期无人问津，很多人跑过来看看 zsh 的配置指南，什么都不说转身就走了。直到有一天，国外有个穷极无聊的程序员开发出了一个能够让你快速上手的zsh项目，叫做「oh my zsh」，Github 网址是：https://github.com/robbyrussell/oh-my-zsh。这玩意就像「X天叫你学会 C++」系列，可以让你神功速成，而且是真的。好，下面我们看看如何安装、配置和使用 zsh。 

##安装 oh my zsh
首先安装 git，安装方式同上，把 zsh 换成 git 即可。
安装「oh my zsh」可以自动安装也可以手动安装。
###自动安装：
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
###手动安装
    git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
安装完成之后退出当前会话重新打开一个终端窗口，你就可以见到这个彩色的提示了：
![ohmyzsh.png](http://d.pcs.baidu.com/thumbnail/5e64051020a14c54d70a92a43a6dd58c?fid=2401735589-250528-921043448399174&time=1458183600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-%2F0rshAfnkGo93kgIOBQupvjQx4Q%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=1774228807894188603&dp-callid=0&size=c710_u500&quality=100)

##配置
zsh 的配置主要集中在用户当前目录的.zshrc里，用 vim 或你喜欢的其他编辑器打开.zshrc，在最下面会发现这么一行字：
##### Customize to your needs…
可以在此处定义自己的环境变量和别名，当然，oh my zsh 在安装时已经自动读取当前的环境变量并进行了设置，你可以继续追加其他环境变量。
###接下来进行别名的设置，我自己的部分配置如下：
    alias cls='clear'
    alias ll='ls -l'
    alias la='ls -a'
    alias vi='vim'
    alias javac="javac -J-Dfile.encoding=utf8"
    alias grep="grep --color=auto"
    alias -s html=mate   # 在命令行直接输入后缀为 html 的文件   名，会在 TextMate 中打开
    alias -s rb=mate     # 在命令行直接输入 ruby 文件，会在 TextMate 中打开
    alias -s py=vi       # 在命令行直接输入 python 文件，会用 vim 中打开，以下类似
    alias -s js=vi
    alias -s c=vi
    alias -s java=vi
    alias -s txt=vi
    alias -s gz='tar -xzvf'
    alias -s tgz='tar -xzvf'
    alias -s zip='unzip'
    alias -s bz2='tar -xjvf'
#####TIP:更多设置请自行google
设置完环境变量和别名之后，基本上就可以用了，如果你是个主题控，还可以玩玩 zsh 的主题。在 .zshrc 里找到ZSH_THEME，就可以设置主题了，默认主题是：

ZSH_THEME=”robbyrussell”

oh my zsh 提供了数十种主题，相关文件在~/.oh-my-zsh/themes目录下，你可以随意选择
