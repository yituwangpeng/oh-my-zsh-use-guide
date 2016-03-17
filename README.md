#oh my zsh使用指南
##Overview
Shell是Linux/Unix的一个外壳，它负责外界与Linux内核的交互，接收用户或其他应用程序的命令，然后把这些命令转化成内核能理解的语言，传给内核，内核是真正干活的，干完之后再把结果返回用户或应用程序。Linux/Unix提供了很多种Shell，常用的Shell有这么几种，sh、bash、csh等，想知道你的系统有几种shell，可以通过以下命令查看：

    cat /etc/shells 
####结果输出如下：
    /bin/bash
    /bin/csh
    /bin/ksh
    /bin/sh
    /bin/tcsh
    /bin/zsh   
在 Linux 里执行这个命令和 Mac 略有不同，你会发现 Mac 多了一个 zsh，也就是说 OS X 系统预装了个 zsh，这是个神马 Shell 呢？目前常用的 Linux 系统和 OS X 系统的默认 Shell 都是 bash，但是真正强大的 Shell 是深藏不露的 zsh， 提供了极强的可定制性和可扩展性，以及一些有趣的功能，比如：

* 自定义提示符，可以与git等软件集成；
* 可编程的命令补全，例如输入kill命令后按tab会自动列出进程；
* 全局可共享、并且能以各种方式管理的命令历史；
* 命令补全错误纠正、界面主题包、不输入cd只输入目录名直接进入目录……

但是由于配置过于复杂，所以初期无人问津，很多人跑过来看看 zsh 的配置指南，什么都不说转身就走了。直到有一天，国外有个穷极无聊的程序员开发出了一个能够让你快速上手的zsh项目，叫做「oh my zsh」，Github 网址是：https://github.com/robbyrussell/oh-my-zsh。这玩意就像「X天叫你学会 C++」系列，可以让你神功速成，而且是真的。好，下面我们看看如何安装、配置和使用 zsh。 

##安装 oh my zsh

安装「oh my zsh」可以自动安装也可以手动安装。

###自动安装：
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
###手动安装
    git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
安装完成之后退出当前会话重新打开一个终端窗口，你就可以见到这个彩色的提示了：
![ohmyzsh.png](http://d.pcs.baidu.com/thumbnail/5e64051020a14c54d70a92a43a6dd58c?fid=2401735589-250528-921043448399174&time=1458183600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-%2F0rshAfnkGo93kgIOBQupvjQx4Q%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=1774228807894188603&dp-callid=0&size=c710_u500&quality=100)

##配置
zsh 的配置主要集中在用户当前目录的.zshrc里，用 vim 或你喜欢的其他编辑器打开.zshrc，
每一行的配置前面都有#号,如果想要配置生效,去掉 #号即可.下面只罗列几个可能用到的,大部分的我还没有去琢磨.

ZSH_THEME="robbyrussell"  //用来指定zsh 样式,就像我上面的截图一样.

####接下来进行别名的设置，我自己的部分配置如下：
    alias cls='clear'
    alias ll='ls -l'
    alias la='ls -a'
    alias vi='vim'
    ...
    TIP:更多设置请自行google

设置完环境变量和别名之后，基本上就可以用了，如果你是个主题控，还可以玩玩 zsh 的主题。在 .zshrc 里找到ZSH_THEME，就可以设置主题了，默认主题是：

ZSH_THEME=”robbyrussell”

oh my zsh 提供了数十种主题，相关文件在~/.oh-my-zsh/themes目录下，你可以随意选择

##插件

oh my zsh 项目提供了完善的插件体系，相关的文件在~/.oh-my-zsh/plugins目录下，默认提供了100多种，大家可以根据自己的实际学习和工作环境采用，想了解每个插件的功能，只要打开相关目录下的 zsh 文件看一下就知道了。插件也是在.zshrc里配置，找到plugins关键字，你就可以加载自己的插件了，系统默认加载 git ，你可以在后面追加内容.
因为我们主要配合git使用，讲一下git插件：

* git：当你处于一个 git 受控的目录下时，Shell 会明确显示 「git」和 branch，如上图所示，另外对 git 很多命令进行了简化，例如 gco=’git checkout’、gd=’git diff’、gst=’git status’、g=’git’等等，熟练使用可以大大减少 git 的命令长度，命令内容可以参考~/.oh-my-zsh/plugins/git/git.plugin.zsh

* 其他插件使用还靠自己google学习了

##结束语

本小短文简单明了的讲解oh my zsh的使用，主要是给项目新成员普及入门使用。更多酷炫好玩的功能还靠大家自行发掘。
                                          
####write by yitu
                                          
####2016.3.17




