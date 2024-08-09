//参考自：https://www.cnblogs.com/FengZeng666/p/14956178.html

本项目通过operator-sdk生成一个项目。项目首先需要下载operator-sdk安装包。在github中，找到适合自己版本的sdk。https://github.com/operator-framework/operator-sdk/releases
选好之后，右键需要的版本并复制链接。
到ubantu的终端中，输入：    （后面的网址就是刚刚复制的链接）

[root@master ~]# wget https://github.com/operator-framework/operator-sdk/releases/download/v1.9.0/operator-sdk_linux_amd64

之后添加可执行权限、复制到/usr/local/bin下即可(因为Linux中的PATH默认包含/usr/local/bin，这点可以使用echo $PATH验证)。

#添加可执行权限

[root@master ~]# chmod +x operator-sdk_linux_amd64

#将此二进制文件复制到/usr/local/bin/目录下，并改名为operator-sdk

[root@master ~]# cp operator-sdk_linux_amd64 /usr/local/bin/operator-sdk  

#安装成功，查看版本
[root@master ~]# operator-sdk version

需要注意的是，operator-sdk需要与合适的golang版本一起使用才行。一开始我下的operator-sdk版本是1.36.0，golang版本是1.16。但是在init的时候会报错，后面百度之后发现是因为golang版本不够的原因。后面把golang升级到1.22.5之后顺利init成功（就是demo文件）。

本项目提供了使用的operator-sdk和golang版本。
