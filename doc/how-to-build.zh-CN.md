# Navicat Keygen - 如何编译？

## 1. 前提条件

1. 请确保你安装了下面几个库：

   * `gcc g++`
   * `openssl header`
   * `capstone`
   * `keystone`
   * `rapidjson`

   你可以通过下面的命令来安装它们：

   ```console
   # install gcc g++
   $ sudo apt-get install build-essential
   
   # install openssl header
   $ sudo apt-get install libssl-dev
   
   # install capstone
   $ sudo apt-get install libcapstone-dev

   # install keystone
   $ sudo apt-get install cmake
   $ git clone https://github.com/keystone-engine/keystone.git
   $ cd keystone
   $ mkdir build
   $ cd build
   $ ../make-share.sh
   $ sudo make install
   $ sudo ldconfig

   # install rapidjson
   $ sudo apt-get install rapidjson-dev
   ```

2. 你的gcc要支持C++17特性。
3. 通过 ubuntu18.04 测试，gcc7.4 官方自带的二进制软件包并不支持 c++17 特性，尽管从 gcc7.1 稳定版开始就支持 c++17。所以我是偷懒用了ubunt20.04的源安装了gcc9.3版本，支持 c++17。
   ```bash
   不支持 c++17，会抛出异常如下
   ./navicat-patcher/Misc.cpp:6:10: fatal error: filesystem: No such file or directory
   ```

## 2. 编译

```console
$ git clone -b main --single-branch https://github.com/liangtiansheng/navicat-keygen.git
$ cd navicat-keygen
$ make all
```

生成完成后，你会在 `bin/` 文件夹下看到编译后的keygen/patcher。
