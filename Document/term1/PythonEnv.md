## 修改 Raspi-config,

- 开启 I2C;
- 开启 Advanced Options - Expand Filesystem so you can use your whole sd-card storage
  > 在 Raspberry Pi（树莓派）中，I2C 也被用于相似的目的。它允许你连接各种设备，如温度传感器、LCD 显示器、数字加速度计等，并通过 I2C 协议与它们通信。这使得 Raspberry Pi 可以收集和处理来自这些设备的数据，或者控制它们执行特定的操作。
  > I2C 有两条线路，一条是数据线（SDA），另一条是时钟线（SCL）。数据线用于在设备之间传输数据，而时钟线用于同步所有设备的数据传输。这种设计使得 I2C 可以在只使用两条线的情况下，链接并控制多个设备。

## 修改 apt-get 源

[Ref](https://zhuanlan.zhihu.com/p/487016386)

## download

```bash
python3 -m venv env --system-site-packages
sudo apt install libcap-dev
pip install donkeycar[pi]
```

启动环境命令：`source ~/env/bin/activate`,设置了别名,输入`qidong`即可进入虚拟环境

## Validation

```bash
python -c "import tensorflow; print(tensorflow.__version__)"
```

![image-20240403220312748](assets/image-20240403220312748.png)

## 下载 Python 代码

`git clone https://githubfast.com/autorope/donkeycar.git`
