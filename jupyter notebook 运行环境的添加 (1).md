@[TOC](jupyter notebook 运行环境的添加)

# 关于Anaconda的下载

1.可以去官网下载最新版的Anaconda：https://www.anaconda.com/products/individual（官网下载速度较慢）
   2. 可以去清华大学软件镜像站下载：https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive（比较推荐）
    注：不会下载的去问百度吧，也不会百度的还是别下载了，没用！！！
## 新的运行环境的创建

第一种方法.直接使用Anaconda Navigator
   找到anaconda navigator 快捷方式之后打开![](https://img-blog.csdnimg.cn/2020080216480742.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDUwNzg5Mg==,size_16,color_FFFFFF,t_70)
   这里我已经新建过一个运行环境了，所以会出现两个，正常应该只有base
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200802165051652.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDUwNzg5Mg==,size_16,color_FFFFFF,t_70)
python版本根据自己电脑里的版本选择，名字起自己能分得清的名字就行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200802165240338.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDUwNzg5Mg==,size_16,color_FFFFFF,t_70)
第二种方法.直接创建新的运行环境
创建一个名为shanow的环境，指定Python版本是3.8.1
```python
conda create --name shanow python=3.8.1
```
创建好之后会在Anaconda3安装目录里的 /envs/ 文件夹里 多了一个shanow文件夹，这个就是刚刚创建的新的环境
然后激活环境，用activate激活

```python
activate shanow 
```
这样一个新的运行环境就创建好了，下面就可以在jupyter notebook里添加新的运行环境了
## 向jupyter notebook里添加kernel（创建好的运行环境）
先安装ipykernel

```python
pip install ipykernel
```
装好后执行下面代码

```python
conda install nb_conda_kernels
```

然后重启 jupyter notebook就可以了
也可以自己手动导入创建好的运行环境

```python
python -m ipykernel install --user --name shanow --display-name "Python383"
```
代码里的shanow为创建的运行环境的名字，最后的Python383是自己想要这个运行环境在jupyter notebook里显示的名字
之后再重新打开jupyter notebook就可以了
## jupyter notebook 删除指定kernel
1.查看所有运行环境

```python
jupyter kernelspec list
```
2.卸载运行环境
代码里的kernel_name为运行环境的名字
```python
jupyter kernelspec remove kernel_name
```
3.删除之后可以在执行查看代码检查一下

```python
jupyter kernelspec list
```
然后再重启jupyter notebook之后就可以看见之前那个运行环境被删除了

