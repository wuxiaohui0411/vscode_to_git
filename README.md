# 前提条件
> 本地电脑需要安装Git

Git官网地址(https://git-scm.com/downloads)

下载windows客户端安装包,直接安装就行,傻瓜式操作
![](Image/Snipaste_2022-10-15_20-57-19.png)

通过scoop命令下载安装git

![](Image/Snipaste_2022-10-15_21-01-17.png)

配置git 的用户名以及邮箱

```Powershell
git config --global user.name "wuxiaohui"

git config --global user.email "wuxiaohui0411@gmail.com"
```

![](Image/Snipaste_2022-10-15_21-15-27.png)


# 配置SSH

## 本地SSH配置密钥

打开PowerShell

配置ssh密钥

```Powershell
ssh-keygen
```
在家目录下会生产一个`.ssh`的隐藏目录

![](Image/Snipaste_2022-10-15_20-50-56.png)

```powershell
cd ~/.ssh
ls
cat ./id_rsa.pub
```

该目录下会有两个密钥,分为公钥、私钥

需要复制公钥的信息

![](Image/Snipaste_2022-10-15_20-51-37.png)

## github配置ssh公钥

### 进入个人Github主页,点击设置
![](Image/Snipaste_2022-10-15_20-52-09.png)

### 左侧菜单栏找到`SSH and GPG keys`,配置新的SSH Key
![](Image/Snipaste_2022-10-15_20-52-33.png)

### 将之前复制的公钥信息进行复制
![](Image/Snipaste_2022-10-15_20-53-27.png)

现在Github Web端与本地电脑已经可以进行ssh通信

![](Image/Snipaste_2022-10-15_20-53-52.png)

## github创建新的repository

### 进行资源主页
![](Image/Snipaste_2022-10-15_20-54-08.png)

### 选择新建
![](Image/Snipaste_2022-10-15_20-54-22.png)

### 创建资源可以选择公开或私有
![](Image/Snipaste_2022-10-15_20-55-24.png)

### 创建成功之后,资源内容页可以复制SSH克隆地址
![](Image/Snipaste_2022-10-15_20-56-07.png)

### 通过命令行克隆仓库

在.ssh目录下创建config的文件,复制以下内容

![](Image/Snipaste_2022-10-15_21-08-58.png)

![](Image/Snipaste_2022-10-15_21-08-44.png)
```
Host *
  KexAlgorithms +diffie-hellman-group14-sha1
```

![](Image/Snipaste_2022-10-15_21-11-16.png)


### 通过命令行同步本地文件至Web端

```powershell
git add .
git commit -m "wuxiaohui"
git pull
```

![](Image/Snipaste_2022-10-15_21-21-19.png)



## 通过VScode控制台克隆仓库(傻瓜式操作)

![](Image/Snipaste_2022-10-15_20-59-02.png)

![](Image/Snipaste_2022-10-15_21-03-36.png)

![](Image/Snipaste_2022-10-15_21-03-58.png)


![](Image/Snipaste_2022-10-15_21-04-55.png)

## 通过VScode控制台同步本地文件

![](Image/Snipaste_2022-10-15_21-12-41.png)
![](Image/Snipaste_2022-10-15_21-13-00.png)
![](Image/Snipaste_2022-10-15_21-13-13.png)

![](Image/Snipaste_2022-10-15_21-15-41.png)

## 配置gitlab

![](Image/Snipaste_2022-10-15_21-23-39.png)
![](Image/Snipaste_2022-10-15_21-24-10.png)



