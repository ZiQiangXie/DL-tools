Road_of_ubuntu

linux命令

解压tar

tar -zxvf xxxx.tar.gz

tar -xvJf  xxxx.tar.xz    # .xz结尾是打包后再压缩的文件，外面是xz压缩方式，里面是tar打包方式；

等价于：xz -d xxx.tar.xz    tar -xvf xxx.tar



开启代理：

安装软件tinyproxy：sudo apt-get install tinyproxy

打开：/etc/tinyproxy.conf 或 /etc/tinyproxy/tinyproxy.conf 

修改：

Port 8888                          # 预设是8888 Port,你可以更改

Allow 127.0.0.1                # 将127.0.0.1改成你自己的IP

​                                           # 例如你的IP 是1.2.3.4,你改成Allow 1.2.3.4,那只有你才可以连上这个Proxy

​                                          # 若你想任何IP都可以连到Proxy在Allow前面打#注释

启动：sudo service tinyproxy start

参考： https://blog.csdn.net/qq_27047075/article/details/104164043



使用代理：

vi ~/.bashrc

添加：

export http_proxy="http://10.20.20.131:1392"
export https_proxy="http://10.20.20.131:1392"

source ~/.bashrc

支持Windows软件开启ie代理、http。



nccl安装

sudo apt install libnccl2=2.11.4-1+cuda10.2 libnccl-dev=2.11.4-1+cuda10.2



环境问题：

ModuleNotFoundError: No module named ‘MultiScaleDeformableAttention‘

问题原因：有些代码需要单独的库文件。提示缺少库文件，该库不是Python的库，而是需要自己编译的一个库。

可以查看原始代码的readme文件里面的安装教程。以DINO为例，需要编译。

```python
cd ./models/dino/ops
python setup.py build install
```



低版本gcc安装

gcc-4

在/etc/apt/sources.list中加入两行。

```python
deb http://dk.archive.ubuntu.com/ubuntu/ xenial main
deb http://dk.archive.ubuntu.com/ubuntu/ xenial universe
```

然后sudo apt update。

```python
sudo apt-get install gcc-4.7 gcc-4.7-multilib g++-4.7 g++-4.7-multilib
```

【参考】https://blog.csdn.net/broliao/article/details/104613443

gcc-5/7/9

【参考】https://blog.csdn.net/wowbing2/article/details/117962272

查看gcc

dpkg -l | grep gcc

which gcc

配置切换gcc版本。

查看软连接：sudo update-alternatives --config gcc

如果提示：update-alternatives: error: no alternatives for gcc

【参考】https://blog.csdn.net/krokodil98/article/details/113394752

https://blog.csdn.net/uniqueyyc/article/details/85407693





CUDA相关

安装cuda指定位置。

sudo sh ./cuda_10.2.89_440.33.01_linux.run --toolkitpath=/home/xieziqiang/cuda/cuda-10.2/ --toolkit --silent

安装cudnn

老版本cudnn下载。

https://developer.nvidia.cn/rdp/cudnn-archive

sudo cp cuda/lib64/* /home/xieziqiang/cuda/cuda-10.2/lib64
sudo cp cuda/include/cudnn.h /home/xieziqiang/cuda/cuda-10.2/include

参考：https://blog.csdn.net/kxqt233/article/details/113825524



cuda卸载

卸载的实现方法
那么如何正确、完全的卸载cuda呢？

其实cuda安装时就已经准备好了卸载的接口，卸载程序在/usr/local/cuda-xx.x/bin下，需要注意的是cuda10.0及之前的版本卸载程序名为uninstall_cuda_xx.x.pl，而cuda10.1及之后的版本卸载程序名为cuda-uninstaller。
找到之后运行卸载程序即可，这里的xx.x表示自己的cuda版本。
在命令行中卸载
注意把下边的xx.x替换为自己的cuda版本。
cuda10.0及以下的卸载：

```python
cd /usr/local/cuda-xx.x/bin/
sudo ./uninstall_cuda_xx.x.pl
sudo rm -rf /usr/local/cuda-xx.x
```

cuda10.1及以上的卸载：

```python
cd /usr/local/cuda-xx.x/bin/
sudo ./cuda-uninstaller
sudo rm -rf /usr/local/cuda-xx.x
```

最后边加了一句sudo rm -rf /usr/local/cuda-xx.x，这是因为一般情况下cuda都配置了cudnn，在运行卸载程序时只会卸载cuda而不会一并删除cudnn的文件。因为cudnn文件还在的缘故，自己的cuda-xx.x文件夹仍然在，需要手动删除。
所以如果自己要卸载的cuda没有配置cudnn，那么cuda-xx.x文件夹在卸载完成后会被自动删除，也就没必要再运行最后一句了。
【参考】https://blog.csdn.net/weixin_44711603/article/details/110233047



错误： fatal error: cuda_runtime.h: 没有那个文件或目录

打开环境变量文件：vim ~/.bashrc

在最后添加：export CPATH=/usr/local/cuda/targets/x86_64-linux/include:$CPATH

然后激活一下：source ~/.bashrc

其中/usr/local/cuda为系统安装的cuda的路径，如果不一样需要自行替换；

备注：export LD_LIBRARY_PATH=/usr/local/cuda-10.1/targets/x86_64-linux/lib:$LD_LIBRARY_PATH，这条命令应该是不需要的。

【参考】https://blog.csdn.net/weixin_45617478/article/details/116209903



错误：/bin/sh: 1:/bin/nvcc: not found

查看nvcc是否存在，不存在需要安装cuda。

which nvcc

whereis nvcc

nvcc -V

打开环境变量文件：vim ~/.bashrc

在最后添加：export CUDA_HOME=/usr/local/cuda

然后激活一下：source ~/.bashrc

其中/usr/local/cuda为系统安装的cuda的路径，如果不一样需要自行替换；

注意：CUDA_HOME比较特殊，不带$CUDA_HOME。

cuda相关的完整的环境变量：

```python
export CPATH=/usr/local/cuda/targets/x86_64-linux/include:$CPATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
export CUDA_HOME=/usr/local/cuda
export PATH=/usr/local/cuda/bin:$PATH
```

【参考】https://blog.csdn.net/weixin_44153180/article/details/131061325?spm=1001.2101.3001.6650.4&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-4-131061325-blog-132598503.235%5Ev38%5Epc_relevant_sort&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-4-131061325-blog-132598503.235%5Ev38%5Epc_relevant_sort&utm_relevant_index=5

https://blog.csdn.net/BetrayFree/article/details/132598503?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EYuanLiJiHua%7EPosition-3-132598503-blog-100019901.235%5Ev38%5Epc_relevant_sort&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EYuanLiJiHua%7EPosition-3-132598503-blog-100019901.235%5Ev38%5Epc_relevant_sort&utm_relevant_index=6



TensorRT安装

官网下载，需要登录。注意查看与cuda和cudnn的匹配关系。

尽量下tar压缩包。

参考：

https://blog.csdn.net/weixin_43605641/article/details/126744446

https://blog.csdn.net/qq_37541097/article/details/114847600

https://blog.csdn.net/IAMoldpan/article/details/117908232



conda相关

跨服务器迁移conda虚拟环境

1）将源环境拷贝到新服务器的任意位置

源虚拟环境：path/miniconda3/envs/ori_name

2）在目标服务器上：

conda create -n new_name --clone 拷贝环境存放的路径

用个人账户会建立在~/.conda/envs路径下，与系统conda环境不冲突。

用root账户，才会上建立到本机conda的目录内，所有用户共享。

【参考】https://blog.csdn.net/qq_41967982/article/details/115867230

https://blog.csdn.net/sunmenmian/article/details/120954958

在任意位置创建新环境。

将已有环境env1克隆到env2，并指定env2的路径/home/root/env2

conda create -p /home/root/env2 --clone env1

【参考】https://blog.csdn.net/zhouhy0903/article/details/127621869



如果新建的环境变量没有名字，如通过-p指定路径的环境，可以删除。

conda remove -p /home/root/env2 --all

用名字的删除方法：

conda remove -n your_env_name --all

conda env remove --name your_env_name



各种源地址：

https://mirrors.aliyun.com/pypi/simple/

https://pypi.tuna.tsinghua.edu.cn/simple/

https://mirror.baidu.com/pypi/simple

https://mirrors.cloud.tencent.com/pypi/simple

pip install xxx -i Դ

https://paddlepaddle.org.cn/whl/mkl/stable.html
https://www.paddlepaddle.org.cn/whl/linux/mkl/avx/stable.html

torch、torchvision：https://download.pytorch.org/whl/torch_stable.html

mmcv:

https://github.com/open-mmlab/mmcv/issues/1818

https://download.openmmlab.com/mmcv/dist/cu92/torch1.7.0/index.html

替换cu92、torch1.7.0，可以对应下载版本；



解决libstdc++.so.6: version `GLIBCXX_3.4.22' not found

虚拟环境中安装库时报错，可先找找对应的库，看看版本是否包含；
strings path/anaconda3/envs/tensorflow/lib/libstdc++.so.6 |grep GLIBCXX  

下载一个  http://ftp.de.debian.org/debian/pool/main/g/
或者取其他服务器拷贝一个
/usr/lib/x86_64-linux-gnu/libstdc++.so.6.0.25   先找一下对应的版本；

cp libstdc++.so.6.0.25  path/anaconda3/envs/tensorflow/lib/

cd ~/anaconda3/envs/tensorflow/lib/

rm libstdc++.so.6

ln libstdc++.so.6.0.25 libstdc++.so.6