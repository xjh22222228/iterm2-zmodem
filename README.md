

`sz` 即 `send Zmodem`，就是用Zmodem文件传输协议从Linux服务器发送文件到客户端的意思，`rz` 则就是 `receive Zmodem` ，从字面就很容易理解是在Linux上接收文件，也就是上传了。


## 服务器安装
```bash
yum install lrzsz -y
```

## 使用
上传文件到服务器，直接敲 `rz` 即可
```
rz
```
![](https://xiejiahe.gitee.io/picture-bed/img/105.png)



下载文件到客户端, `sz` 后跟需要下载的文件路径
```bash
sz fileName
```
![](https://xiejiahe.gitee.io/picture-bed/img/106.png)



## MAC OS配置
在mac上就有点麻烦了。

mac自带的终端是不支持的，需要安装 `iTerm2` ，这里不介绍如何安装。

安装 `lrzsz`
```
brew install lrzsz
```


**下载 iTerm2 脚本文件, 执行以下3条命令：**

1、进入到 `bin` 目录，我们要把脚本下载到此目录
```bash
cd /usr/local/bin
```

2、下载`iterm2-recv-zmodem.sh`
```
sudo wget https://raw.githubusercontent.com/xjh22222228/iterm2-zmodem/master/iterm2-recv-zmodem.sh
```

3、下载`iterm2-send-zmodem.sh`
```
sudo wget https://raw.githubusercontent.com/xjh22222228/iterm2-zmodem/master/iterm2-send-zmodem.sh
```

4、赋予权限
```bash
sudo chmod 777 iterm2-*
```

如无法下载 [点击这里](https://github.com/xjh22222228/iterm2-zmodem) 到github仓库自行下载。



**配置iTerm2**
1、打开 iTerm2 => Preferences => Profiles => Advanced => Triggers Edit

![](https://xiejiahe.gitee.io/picture-bed/img/107.png)



2、点击 `+` 新增以下2条:

`\*\*B0100　　　　　　　Run Silent Coprocess　　/usr/local/bin/iterm2-send-zmodem.sh   打勾`

`\*\*B00000000000000　 Run Silent Coprocess　　/usr/local/bin/iterm2-recv-zmodem.sh  打勾`

![](https://xiejiahe.gitee.io/picture-bed/img/108.png)


至此配置完成,  在 `iTerm2` 打开新的终端即可使用。

最后附上一张预览图：
![](https://xiejiahe.gitee.io/picture-bed/img/109.gif)

