Road_of_vscode



快捷操作

跳转到定义：  F12  Ctrl + 鼠标左键

跳回上一次位置：  Alt + 左箭头   鼠标回退键（若有）

多行同时修改：Ctrl + Alt + 上下箭头，选择多行同时修改（插入、删除等）；

快速复制一行：Shift +  Alt + 上下箭头，向上/下复制当前行；

左右分屏显示：Ctrl + Alt + 左右箭头；

多行注释/取消注释：选择多行，Ctrl + /





vscode配置c/c++环境

【参考】https://blog.csdn.net/zimuzi2019/article/details/106861692



vscode远程开发配置参考：https://www.cnblogs.com/tavonl/p/14769862.html

1、配置

* 本地机器：Win10/win7
* 远程服务器：Ubuntu 18/20.04 LTS
* 已配置ssh
* 已安装MobaXterm

2、简介

X 协议2由 X server 和 X client 组成：

X server 管理主机上与显示相关的硬件设置（如显卡、硬盘、鼠标等），它负责屏幕画面的绘制与显示，以及将输入设置（如键盘、鼠标）的动作告知 X client。
X client 则主要负责事件的处理（即程序的逻辑）。它会向X server反馈事件处理结果。
上图表示 X server 和X client不在同一台主机上依然可以按照X协议进行通讯，也就是说我们可以将远程服务器设置成X client,本地机器设置成X server，在两者之间建立通讯即可达成远程服务器处理生成图像的事件，然后反馈到本地机器上让本地机器生成结果。

3、实现步骤

* 本地端

3.1 X server准备
MobaXterm是集成了X server和ssh的一个非常好用的客户端，可以很方便的查看服务器文件并且能拖拽文件达成在本地机器和服务器之间进行文件传输的目的。

安装了MobaXterm后，在Settings->Configuration->X11将X11 remote access选项改选为full。

3.2 vscode设置
在vscode软件中的extensions中搜索Remote X11，并点击安装 。

打开remote-ssh设置。（在C:\Users\你的用户名\.ssh\config）

在config文件中添加3行设置：

```python
ForwardX11 yes
ForwardX11Trusted yes
ForwardAgent yes
```

* 服务端

3.4 检查配置文件
查阅资料23发现需要设置配置文件，输入命令：

```python
sudo vim /etc/ssh/sshd_config
```

结果发现我的配置文件已经有相关设置。

```python
X11Forwarding yes
#X11DisplayOffset 10
#X11UseLocalhost yes
```

结合资料应该是必须要设置这两项。(我的配置文件没有设置X11UseLocalhost，可能是默认为no了)

```python
X11Forwarding yes
X11UseLocalhost no   #禁止将X11转发请求绑定到本地回环地址上
```

3.5 设置环境变量
据查阅资料4，MobaXterm 上的X server启动后默认会监听本地6000端口。X client通过环境变量DISPLAY获取X server服务地址，例如DISPLAY=本机ip地址:0.0，代表X server在本机6000端口，DISPLAY=本机ip地址:1.0，代表X server在本机6001端口依此类推。

给服务器增加DISPLAY环境变量，修改.bashrc文件：

vim ~/.bashrc
在文件中加一句：

export DISPLAY=你的本地主机ip:0.0

最后输入命令生效一下：

source ~/.bashrc

4、验证

跑了一下mmdet，可以在本地输出目标检测结果图了

再尝试跑了一下open3d,也可以可视化点云了。

支持cv2.imshow等可视化。

也可以参考：

vscode远程连接服务器+X11插件图形化界面

https://blog.csdn.net/Stone_hello/article/details/120041495



pycharm或者vscode利用moba-xterm的x server远程开发，在使用cv2显示图片时报错ASSERT false in file qasciikey.cpp, line 501。

解决：moba-xterm > settings > x11 Settings > "Unix-compatible keyboard" 的复选框不要勾选，然后按照提示会自动重启x server，重新在pycharm或vscode运行代码就可以了



cv2.imshow/namedwindow等函数报错：install libgtk2.0-dev and pkg-config

sudo apt-get install libgtk2.0-dev

安装之后，需要重新卸载并安装一下opencv_contrib_python，这个库安装是默认会关联gtk相关的依赖，如果之前没有装gtk则无法关联，所有安装gtk后需要重新安装一下。



vscode ubuntu配置cmake编译、c/c++调试等

https://blog.csdn.net/weixin_44120025/article/details/118930038

https://blog.csdn.net/weixin_42398658/article/details/121784380



插件/扩展：

历史版本下载参考：https://github.com/microsoft/vscode-python/discussions/20184



调试

launch.json配置。

```python
    "version": "0.2.0",
    "configurations": [

        {
            "name": "Python: 当前文件",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "justMyCode": false,
            "args": ["xxx", "xxx"],
            "env": {"CUDA_VISIBLE_DEVICES": "3", "FLAGS_set_to_1d": "False"}
        }
    ]
}
```

说明：

program：指定要运行的文件，可填相对路径，如 tools/train.py，是相对于当前工程的根目录。

justMyCode：是否只在当前代码中调试，默认为true，改为false，可以进入调用的库中；

args：可选，默认没有，该参数可以用于对要运行的文件传参，将实际运行时要用到的所有参数按照顺序写入；

env：可选，默认没有，环境变量，该参数可以用于指定运行的环境变量，如通过 export 指定 GPU 等；