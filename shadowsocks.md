# Ubuntu下使用Shadowsocks科学上网

- 仅供实验室内部交流使用

## 1.安装Shadowsocks-qt5

```bash {.line-numbers}
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```

## 2.安装GenPAC

在多数情况下，我们更希望使用PAC模式的代理，让我们访问国内网站时不再先绕地球跑一圈，在Windows和Mac上的shadowsocks客户端可以轻松切换到PAC模式，而在Ubuntu上我们需要使用pac文件来设置系统代理以达到相同的效果

``` bash {.line-numbers}
#首先安装pip
sudo apt-get install python-pip
#通过pip安装genpac
sudo pip install genpac
```

## 3.配置shadowsock-qt5
1. 同时打开[得自由](https://devpn.info/)（没有账号的可以用文末所给的二维码），点击右上角`用户名`>`我的服务`>按住`ctrl`并滑动滚轮使二维码占据整个屏幕，然后放着不动，进行下一步。


2. 打开`shadowsock-qt5`

![Screenshot from 2017-11-22 10-47-30](https://i.loli.net/2017/11/22/5a1508a3ca2cf.png)

![Screenshot from 2017-11-22 10-49-39](https://i.loli.net/2017/11/22/5a1509762c04a.png)

依次点击 `connection` >  `Add` > `Scan QR on Screen`

![Screenshot from 2017-11-22 11-10-28](https://i.loli.net/2017/11/22/5a150ae9eb821.png)

建议使用域名作为 Server Address
将得自由中我的服务界面滑到最下方，找到ip对应的域名地址。

**例如：**

![Screenshot from 2017-11-25 19-57-43](https://i.loli.net/2017/11/25/5a195b11d900c.png)

![Screenshot from 2017-11-25 20-02-11](https://i.loli.net/2017/11/25/5a195c19a961a.png)

然后随便给它起个名字，按`OK`保存

![Screenshot from 2017-11-22 11-12-40](https://i.loli.net/2017/11/22/5a150b39304b2.png)

选中`代理`，点击`connect`


3. 确认连接上了之后进行下一步

## 4.使用GenPAC生成pac文件
进行这个步骤需要保证shadowsocks已经连接

``` bash {.line-numbers}
genpac -p "SOCKS5 127.0.0.1:1080" --gfwlist-proxy="SOCKS5 127.0.0.1:1080" --gfwlist-url=https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt --output="autoproxy.pac"
```
此时会生成一个名为autoproxy.pac的文件,位于`/home/{你的用户名}/autoproxy.pac`,例如`/home/xulzee/autoproxy.pac`


## 5.更改系统代理设置
- 进入代理设置 `System settings` -> `Network` -> `Network Proxy`

![Screenshot from 2017-11-22 12-55-36](https://i.loli.net/2017/11/22/5a150bb4641f5.png)

![Screenshot from 2017-11-22 12-55-53](https://i.loli.net/2017/11/22/5a150c6421fe8.png)

- 设置 `Method` 为 `Automatic`
- 设置 `Configuration URL` 为 `autoproxy.pac文件的路径`

``` bash {.line-numbers}
#例如
file:///home/用户名/autoproxy.pac
```

## 6.完成
- 试试能不能访问[Google](https://www.google.com/)
- 还可以将`shadowsocks-qt5`设为开机启动,依次点击`settings`>`General settings`>`start at login`
![Screenshot from 2017-11-22 13-00-08](https://i.loli.net/2017/11/22/5a150dbb9237f.png)
- 二维码
![Screenshot from 2017-11-22 13-00-472](https://i.loli.net/2017/11/22/5a150dd7628a9.png)
![Screenshot from 2017-11-22 13-00-47](https://i.loli.net/2017/11/22/5a150dd7628ab.png)
![Screenshot from 2017-11-22 13-00-471](https://i.loli.net/2017/11/22/5a150dd76b746.png)
