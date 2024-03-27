## 下载系统

下载Raspberry Pi Imager,在EDIT SETTINGS中开启SSH Service,保存后点击继续;软件会自动完成镜像的下载和验证

![image-20240327221944442](assets/image-20240327221944442.png)
![image-20240327222729106](assets/image-20240327222729106.png)


![alt text](assets/image.png)

## SSH

将开发机器与树莓派连接在同一局域网中,然后可用ssh连接树莓派进行远程开发`ssh username@hostname`

```shell
ssh admin@raspberrypi
```

![image-20240327222816736](assets/image-20240327222816736.png)

VSCode连接,下载remote-ssh插件

`Ctrl+Shift+P`打开命令面板,选择Connect to Host-Configure SSH Hosts

![image-20240327222912029](assets/image-20240327222912029.png)

![image-20240327223047422](assets/image-20240327223047422.png)

![image-20240327223056409](assets/image-20240327223056409.png)