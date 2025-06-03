# Multiple

[For Linux Users | Multiple Network Gitbook](https://multiple-network.gitbook.io/multiple-network-gitbook/multiple-node-participation-guide/for-linux-users)

1.下载linux文件

```
wget https://cdn.app.multiple.cc/client/linux/x64/multipleforlinux.tar
```

2.解压文件

```
tar -xvf multipleforlinux.tar
```

3.授权

```
cd multipleforlinux/
chmod +x ./multiple-cli
chmod +x ./multiple-node
```

4.配置参数，最下一行输入`PATH=$PATH:/root/multipleforlinux/`

```
sudo nano /etc/profile
```

5.应用参数

```
source /etc/profile
```

6.回到root目录，授权

```
cd ..
chmod -R 777 multipleforlinux
```

7.运行

```
cd multipleforlinux
```

最好用pm2方式运行

```
pm2 start ./multiple-node --name multiple-node
```

```
pm2 startup
pm2 save
```


8.查看进程

```
ps -ef | grep multiple-node
```

9.绑定钱包

```
./multiple-cli bind --bandwidth-download 100 --identifier [NUMBER] --pin [PIN] --storage 200 --bandwidth-upload 100
```

**备注**：

停止所有multiple-node的进程

```
pkill -f ./multiple-node
```
