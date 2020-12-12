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
### References
* [cmake 主页](https://cmake.org/files)
