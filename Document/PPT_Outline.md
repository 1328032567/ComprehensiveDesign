total 16 pages
项目名：CV树莓派小车
PPT字体：微软雅黑（中文字体） + Mono（代码字体） + Times New Roman（英文字体）
按照开发顺序选
1、项目概述(1)nu
     web控制 + 采集数据 + 自主循迹 + 图像识别
2、项目准备(2)yang
    材料购买 + 环境配置（树莓派环境配置 + docker + python + ssh免密登陆） + Git版本管理（本地管理 + Github文档管理）
3、开发流程(7)
    a、配置树莓派相关引脚，连接到PWM驱动器，控制小车舵机电机(1)yang
    b、校准小车直行转向(1)yang
    c、web控制驾驶(1)qiu
    d、识别图像并处理（CV）(2)gao
    f、控制算法(2)gao & qiu
4、优化开发(4)gao
    a、Git迭代开发(1)gao
    b、zsh shell及其插件 \
    c、编写脚本测试      --(1)ding
    d、ssh免密登陆(1)gao
    e、dockerfile编写，便于他人项目复现(1)yang
5、问题与解决(2)qiu
    (1)
    问题1：i2ctool无法检测PWM驱动器
    解决2：排除代码、驱动、硬件组装问题，发现硬件损害，重新购买
    (1)
    问题1:程序输入文件缺失
    解决2：通过github new issue，得到项目负责人解答
6、成果展示(4)nu
    定速循迹 + 自主循迹 + Web控制 + 图像采集
资料来源：
    1、donkeycar源代码
    2、donkeycar文档
    3、树莓派文档
    4、Google搜索
    5、软件代码
    6、工具官方网站描述
    7、Wiki百科