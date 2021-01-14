## Tmux
### 简介
* Tmux 是一个终端复用神器，能够在单个屏幕中同时创建并操控多个终端。最重要的是，它可以随时从当前屏幕中分离（detach）出去，然后在后台继续运行，并且能够重连（attach）。因此其非常适合在服务器上使用。
* [tmux github](https://github.com/tmux/tmux)上给出的定义为： tmux is a terminal multiplexer: it enables a number of terminals to be created, accessed, and controlled from a single screen. tmux may be detached from a screen and continue running in the background, then later reattached.
### 安装
* Ubuntu系统, 在命令行中运行: 
  `sudo apt install tmux`
* 其他系统的安装可参考官方安装教程[tmux install](https://github.com/tmux/tmux/wiki/Installing)
### 配置
* 推荐[oh my tmux](https://github.com/gpakosz/.tmux)配置，可在该配置的基础上进行个性化适配。
* 上述配置安装: 

```
cd ~
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .
```
### 基本用法
* `tmux`: 创建一个新的会话（session），并自动命名为0
* `tmux new -s name`: 创建一个名字为name的会话
* `tmux ls`: 列出当前所有的会话
* `tmux at -t name`: 恢复（attach）名字为name的会话
* `tmux -V`: 查看tmux版本
* **快捷键绑定**
  * `Ctrl b`: 前置键, 记为`<prefix>`
  * `<prefix> e`: 打开`~/.tmux.conf.local`文件，此文件即为配置文件，可修改以适配自己的习惯。
  * `Ctrl l`: 清屏
  * `<prefix> Ctrl c`: 创建新的会话
  * `<prefix> Ctrl -`: 水平分割窗口
  * `<prefix> Ctrl _`: 垂直分割窗口
  * `<prefix> t`: 显示时间
  * `<prefix> z`: 将当前窗口最大化（返回原状也是该快捷键）
  * `<prefix> m`: 开启鼠标模式
  * `<prefix> 0-9`: 选择0-9窗口
  * `<prefix> ，`: 重命名窗口
### References
* [tmux github](https://github.com/tmux/tmux)
* [tmux install](https://github.com/tmux/tmux/wiki/Installing)
* [oh my tmux](https://github.com/gpakosz/.tmux)
