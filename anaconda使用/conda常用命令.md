# 为什么使用anaconda?
使用anaconda安装tensorflow，caffe、pytorch等框架，可以先通过anaconda创建虚拟环境，然后在不同的虚拟环境下装上不同的版本的框架（例如在一个虚拟环境上安装一个tensorflow1.4，在另一个虚拟环境中上安装一个tensorflow1.6，在另一个虚拟环境中安装pytorch）。并且如果配置出错，直接删除虚拟环境的包即可，而不影响这个系统。
# 创建虚拟环境
#### 创建一个新的虚拟环境
conda create -n env_name python=version
#### 查看已经安装的虚拟环境
conda env list
#### 进入虚拟环境
activate env_name
#### 退出虚拟环境
deactivate
