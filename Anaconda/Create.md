# 创建环境

* 1.打开命令提示符或Anaconda Prompt。
* 2.运行以下命令来创建一个新的环境并指定安装路径：
```
conda create --prefix D:\ProgramData\anaconda3\envs\RD++ python=3.8
```
* 3.当提示是否继续安装时，输入`y`并按回车键确认。
* 4.环境创建完成后，使用以下命令激活该环境：
```
conda activate D:\ProgramData\anaconda3\envs\RD++
```

------------------

# 相关指令

* > 默认路径建立环境：
```
conda create -n your_env_name python=x.x
```
* > 退出当前环境：
```
conda deactivate
```
* > 激活环境（默认）
```
conda activate yolov7test
```
* > 激活环境（指定路径）
```
conda activate D:\xx\xx
```
* > 查看所有已建环境
```
conda info --envs
```

* > 删除环境
```
conda remove -n RD++--python=3.8 --all
```

* > 查看环境下的所有包
```
conda list
```

* > 配置国内源
```
conda config --remove-key channels
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/pytorch/
conda config --set show_channel_urls yes
pip config set global.index-url https://mirrors.ustc.edu.cn/pypi/web/simple
```
