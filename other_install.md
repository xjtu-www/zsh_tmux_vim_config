### cmake
* `sudo apt install cmake`: 该方法下载的版本可能较低。
* 源码编译安装: 
    * 在[cmake 主页](https://cmake.org/files)下载源码，如`cmake-3.15.1.tar.gz`。
    * 解压源码:`tar -zxv -f camke-3.15.1.tar.gz`或`x cmake-3.15.1.tar.gz`。
    * 进入解压后的cmake文件夹。
    * 执行: `./bootstrap`
    * 执行: `make`
    * 执行: `sudo make install`
    * 验证是否安装成功: `cmake --version`
    * 加入系统路径(`.bashrc`或`.zshrc`): `export PATH=/Path/to/cmake-3.15.1/bin:$PATH`
    
### spconv(Spatially Sparse Convolution Library)
* `git clone https://github.com/traveller59/spconv.git --recursive`
* `sudo apt-get install libboost-all-dev`
* Download cmake>=3.13.2
* `python setup.py bdist_wheel`
* **fatal error**解决方法: `sudo apt-get install libboost-all-dev`
* `cd ./dist`
* `pip install *.whl`
* [spconv 主页](https://github.com/traveller59/spconv)

### pcdet(OpenPCDet)
* `git clone https://github.com/open-mmlab/OpenPCDet.git`
* `pip install -r requirements.txt`，有些包的版本最好自己指定一下，如pytorch==1.3。
* [安装spconv1.2](https://github.com/xjtu-www/zsh_tmux_vim_config/blob/main/other_install.md#spconvspatially-sparse-convolution-library)
* `python setup.py develop`
* [pcdet 主页](https://github.com/open-mmlab/OpenPCDet)
### References
* [cmake 主页](https://cmake.org/files)
* [spconv 主页](https://github.com/traveller59/spconv)
* [pcdet 主页](https://github.com/open-mmlab/OpenPCDet)
