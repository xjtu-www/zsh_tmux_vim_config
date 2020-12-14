## Oh My Zsh
### 前言
* **什么是zsh？**
  * zsh全名z shell，顾名思义，它是shell的一种，而且是很powerful的那种。那shell又是什么？通俗地讲，shell就是能够接受用户输入指令的操作界面，像我们常说的“命令行”、“终端”等指的都是shell。shell的种类繁多，但大多数Linux发行版（如Ubuntu）默认使用的均为bash shell。相比于bash，zsh为程序员提供了更多、更好、更灵活的选择，无论是外观（e.g. 丰富的主题）还是实用的插件（插件是灵魂=。=），因此其深受广大码农的青睐。
  * 这里给出[Zsh主页](https://www.zsh.org/)的官方定义：Zsh is a shell designed for interactive use, although it is also a powerful scripting language.
* **什么是oh my zsh?**
  * zsh的强大功能往往伴随着复杂的插件配置过程（发量-n）。为了使zsh用起来更方便快捷，oh my zsh应运而生。oh my zsh主要的功能就是对zsh的插件配置进行统一管理，因此你可以形象地称它为zsh的“配置管家”。
  * 这里给出[Oh My Zsh主页](https://ohmyz.sh/)的官方定义：Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration.
* **为什么要使用zsh or oh my zsh?**
  * 效率：让你的指令操作如德芙般丝滑。
  * 灵活：插件库深似海，总有一款适合你。
  * 成为实验室中最靓的仔：懂的都懂*^*
### oh my zsh 安装（step by step）
* 注：以下安装过程均基于Ubuntu 16.04（Windows系统下的安装可直接参考官方链接[oh my zsh github](https://github.com/ohmyzsh/ohmyzsh)，[Install zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)）
* **安装 zsh**
  * 查看正在使用的shell：`echo $SHELL`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_1.png'></div>
  
  * 查看所有shell：`cat /etc/shells`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_2.png'></div>
  
  * 安装zsh：`sudo apt install zsh`
  * 再次查看所有shell：`cat /etc/shells`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_3.png'></div>
  
  * 查看zsh版本：`zsh --version # 版本最好大于5.0`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_4.png'></div>
  
  * 将zsh设置为默认shell：`chsh -s $(which zsh)`
  * 仅对当前用户设置（适合在服务器上配置时使用）：先输入`chsh`回车, 再输入新的shell路径：`/usr/bin/zsh`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_5.png'></div>
  
  * 重新启动shell（本地需要重启），输入：`echo $SHELL  # 进行验证`
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_6.png'></div>
  
  * 可能遇到的问题：Ignore insecure directories and continue [y] or abort compinit [n]? 输入y，再参考[issue_1](https://github.com/zsh-users/zsh-completions/issues/433)解决
   * **讨论**: Basically, ZSH expects system files to be owned and modifiable (w) by either you (the one running the shell) or root
   * 因此若是普通用户，需联系具有root权限的用户将`compaudit`命令显示的目录的所有者改为root，即运行`sudo chown -R root:root target_directory`命令。
* **安装 oh my zsh**
  * 需预先安装：curl或wget，以及git
  * 在命令行中输入以下命令之一：
    ```
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    sh -c "$(fetch -o - https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" 
    ```
  * 若上述命令执行出错，可直接点击网址进行下载（点击网址后在新弹出的网页右键另存为即可下载install.sh文件），在执行`sh install.sh`命令进行安装。
  * 安装成功后显示：
  
  <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_7.png'></div>
  
### oh my zsh使用
* **配置文件**：完成安装后，会自动在主目录下生成一个隐藏文件~/.zshrc，此即为配置文件，也是最重要的文件。
* **主题**：oh my zsh提供了海量的主题，具体可参考[themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)。找到自己心仪的主题后，只需在配置文件中将ZSH_THEME="robbyrussell"引号中主题名字替换，保存文件后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可。
* **插件**：丰富的插件是zsh的灵魂。可用的插件列表见链接[plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)，每个插件文件夹下都有其对应的README文档供参考。若要使用某插件，只需在配置文件中将插件名字加入到`plugins=()`字段中的括号中即可。注意需以空格或换行来分隔多个插件名，而不能用逗号。修改后保存文件重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可。
### 推荐插件（updating）
* **extract**
  * 功能：一键解压所有格式文件，x file_name或extract file_name
  * 只需在配置文件中加入该插件名'extract'后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可使用。
* **autojump**
  * 功能：自动跳转，具体用法见[autojump](https://github.com/wting/autojump)
  * 安装：在命令行中依次执行：
  ```
  git clone https://github.com/wting/autojump.git
  cd autojump
  ./install.py
  ```
  * 在配置文件中加入该插件名'autojump'后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可使用。
* **zsh-autosuggestions（强烈推荐）**
  * 功能：自动补全，具体用法见[zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions#usage)
  * 安装：在命令行中执行：
  ```
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```
  * 在配置文件中加入该插件名'zsh-autosuggestions'后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可使用。
  * **改键**（由于默认的快捷键较为不方便，因此可按自己习惯进行改键）
    * 打开配置文件，找到source $ZSH/oh-my-zsh.sh，在该行下面新增一句：
    ```
    bindkey '^F' autosuggest-accept
    ```
    * '^F'代表组合键（Ctrl+F），可按自己习惯进行更改。更改后保存文件，重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）。
    
    <div  align="center"><img src='https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/images/fig_8.png'></div>
    
    * 部分补全功能：组合键（Alt+F）或（Esc+F），这是自带的，但大部分博客中都没有提及。
    * 完成上述改建操作后，可以很方便地使用（Ctrl+F）进行全补全，（Alt+F）进行部分补全。
* **zsh-syntax-highlighting（官方主页：[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)）**
  * 功能：语法高亮。
  * 安装：在命令行中执行：
  ```
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```
  * 在配置文件中加入该插件名'zsh-syntax-highlighting'后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可使用。
* **sudo**
  * 功能: 连按两次`Esc`即可在当前命令开头加上`sudo`。
  * 只需在配置文件中加入该插件名'sudo'后重启shell（或直接在命令行中输入`source ~/.zshrc`使配置生效）即可使用。
  
### References
* [Zsh主页](https://www.zsh.org/)
* [Oh My Zsh主页](https://ohmyz.sh/)
* [Install zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH)
* [oh my zsh github](https://github.com/ohmyzsh/ohmyzsh)
* [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions#usage)
* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
* [autojump](https://github.com/wting/autojump)
* [plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)
* [themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
* [issue_1](https://github.com/zsh-users/zsh-completions/issues/433)
### 更新
* 2020-12-09
  * zsh-autosuggestions插件改键。
  * 新增zsh-syntax-highlighting插件。
* 2020-12-14
  * 增加[issue_1](https://github.com/zsh-users/zsh-completions/issues/433)讨论。
  * 新增sudo插件。
