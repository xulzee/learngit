# Ubuntu下安装Matlab-2017a
## 1.安装RAR
```bash {.line-numbers}
sudo apt-get install rar
```
然后将**Matlab 2017a Linux64 Crack**解压到当前文件夹

## 2.安装Matlab
- **安装前请注意将matlab安装文件的路径中的空格删掉**
```bash {.line-numbers}
#例如
/home/xulzee/Downloads/Matlab R2017a linux_x64
#应该修改为
/home/xulzee/Downloads/MatlabR2017alinux_x64
```
- **挂载镜像文件**
```bash {.line-numbers}
#在主目录下创建一个临时文件夹
cd ~
mkdir matlab
#挂载镜像 注意修改为自己的路径名
#/home/xulzee/Downloads/MatlabR2017alinux_x64 为matlab安装文件的地址
#/home/xulzee/matlab/ 为在主目录下创建的临时文件夹的路径名
sudo mount -t auto -o loop /home/xulzee/Downloads/MatlabR2017alinux_x64/R2017a_glnxa64_dvd1.iso /home/xulzee/matlab/
```

- **安装matlab**
```bash {.line-numbers}
sudo ~/matlab/install
```
![Screenshot from 2017-11-25 10-57-20](https://i.loli.net/2017/11/25/5a18dca6c2b0f.png)

![Screenshot from 2017-11-25 11-00-50](https://i.loli.net/2017/11/25/5a18e0625b75f.png)

- key在readme.txt中可以找到，选择这一组：09806-07443-53955-64350-21751-41297

![Screenshot from 2017-11-25 11-01-37](https://i.loli.net/2017/11/25/5a18e06bb3165.png)

![Screenshot from 2017-11-25 11-01-46](https://i.loli.net/2017/11/25/5a18e076e4d92.png)

![Screenshot from 2017-11-25 11-01-52](https://i.loli.net/2017/11/25/5a18e09b5b85a.png)

![Screenshot from 2017-11-25 11-02-09](https://i.loli.net/2017/11/25/5a18e0a39968d.png)
- 需要挂载第二个镜像文件
```
sudo mount -t auto -o loop /home/xulzee/Downloads/MatlabR2017alinux_x64/R2017a_glnxa64_dvd2.iso /home/xulzee/matlab/
```

![Screenshot from 2017-11-25 11-04-20](https://i.loli.net/2017/11/25/5a18e0abb02f9.png)

![Screenshot from 2017-11-25 11-09-15](https://i.loli.net/2017/11/25/5a18e0b3644e4.png)

![Screenshot from 2017-11-25 11-09-19](https://i.loli.net/2017/11/25/5a18e0ba0262a.png)

- 安装完成
```bash {.line-numbers}
umount ~/matlab/
umount ~/matlab/
sudo rm -r ~/matlab/ # 删除空的文件夹
```

## 3.激活Matlab
安装完成后，可以在终端中输入matlab打开软件，如果失败，只能去安装位置打开：

```bash {.line-numbers}
cd /usr/local/MATLAB/R2017a/bin
sudo ./matlab
```
- 选择 activate manually without the internet

![Screenshot from 2017-11-25 19-29-02](https://i.loli.net/2017/11/25/5a19543127268.png)

- 输入破解文件夹中license_standalone.lic的路径(记得删除路径中的空格)

```bash {.line-numbers}
#例如
/home/xulzee/Downloads/MatlabR2017alinux_x64/Matlab2017aLinux64Crack/license_standalone.lic
```

![Screenshot from 2017-11-25 19-22-44](https://i.loli.net/2017/11/25/5a195394b4fb8.png)

- 将破解文件拷贝到对应路径

```bash {.line-numbers}
#将 Matlab2017aLinux64Crack/R2017a/bin/glnxa64 文件中 libmwservices.so
#拷贝到 /usr/local/MATLAB/R2017a/bin/glnxa64
sudo cp /home/xulzee/Downloads/MatlabR2017alinux_x64/Matlab2017aLinux64Crack/R2017a/bin/glnxa64/libmwservices.so /usr/local/MATLAB/R2017a/bin/glnxa64
```

- 再次打开Matlab

```bash {.line-numbers}
cd /usr/local/MATLAB/R2017a/bin
sudo ./matlab
```
![Screenshot from 2017-11-25 19-45-59](https://i.loli.net/2017/11/25/5a19581b0eaab.png)

## 完成！
