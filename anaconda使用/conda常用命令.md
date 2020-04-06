# 1、为什么使用anaconda?
使用anaconda安装tensorflow，caffe、pytorch等框架，可以先通过anaconda创建虚拟环境，然后在不同的虚拟环境下装上不同的版本的框架（例如在一个虚拟环境上安装一个tensorflow1.4，在另一个虚拟环境中上安装一个tensorflow1.6，在另一个虚拟环境中安装pytorch）。并且如果配置出错，直接删除虚拟环境的包即可，而不影响这个系统。

# 2、创建虚拟环境
#### 创建一个新的虚拟环境
conda create -n env_name python=version
#### 查看已经安装的虚拟环境
conda env list
#### 进入虚拟环境
activate env_name
#### 退出虚拟环境
deactivate
#### 删除虚拟环境
conda remove -n env_name --all
#### 删除虚拟环境中的包
conda remove --name $env_name $package_name

# 3、conda包管理
#### 查看包
conda list
### 安装包
#### 3.1 命令安装
conda install package_name(package_name=version) (python=version)
#### 3.2 从指定源安装
1）输入:anaconda search -t conda tensorflow
   这里(anaconda search -t conda 库名)可以选择自己安装的源
2）输入：anaconda show anaconda/tensorflow（anaconda show 对应版本）
3）根据最后一行提示输入：conda install --channel https://conda.anaconda.org/anaconda tensorflow
4）遇到以下：输入YES
5）至此已经安装成功，输入:conda list
#### 3.3 安装cuda和cudnn
当你的系统中已经安装了cuda和cudnn这一步就不需要了，虚拟环境中需要使用的cuda和cudnn会自动调用系统中的。但是如果你的系统的cudnn和cuda版本和所要安装的tensorflow或者pytorch不匹配，就需要在虚拟环境中安装。
通过 conda install cudnn=7.1.2 命令安装cudnn，会自动安装依赖项 cuda（也可以自己通过conda install cuda =9.0自己安装）
#### 3.4 先下载再安装(eg. anaconda3安装jieba)
从官网（https://pypi.org/project/jieba/ ）上下载安装包，解压到anaconda安装目录下的pkgs文件夹下。
1）打开Anaconda Prompt；
2）输入指令cd users\administrator\Anaconda3\pkgs\jieba-0.39（即进入jieba-0.39所在位置）；
3）输入python setup.py install，回车即可（可通过pip list查看是否安装成功）
#### 删除包
conda remove package_name
#### 更新包
conda update package_name
#### 查找包的版本信息
conda search package_name
#### 更新所有包
conda update --all

# 4、分享代码
#### 分享代码的时候,同时也需要将运行环境分享给大家 
conda env export > env.yaml 
#### 用对方分享的 YAML 文件来创建一模一样的运行环境 
conda env create -f env.yaml 
