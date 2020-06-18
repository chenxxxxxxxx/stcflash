# stcflash
  Add support for STC8 series(STC8A,STC8F,STC8H,STC8C) and STC15 series
# 介绍
  stcflash主要是基于https://github.com/laborer/stcflash 的stcflash修改而来，原版的stcflash只支持一些比较旧系列的STC单片机，我在此基础上，添加了对STC8全系列（STC8A、STC8F、STC8H、STC8C）和STC15系列的下载支持。
# 新增功能
1、添加对STC8和STC15系列单片机的下载支持;<br>
2、对于STC8系列和STC15系列，新增最高波特率设置指令--highbaud;<br>
3、对于STC8系列和STC15系列，新增最高波特率支持到460800;<br>
3、新增对于STC8和STC15系列单片机的基本信息读取显示,包括芯片型号、版本、程序空间和出厂序列号等。
# stcflash基本使用方法
## 使用条件
1、需要python环境，推荐python3;<br>
2、安装pyserial模块;<br>
## 使用命令
1、按照默认参数<br>
  ./stcflash.py xxx.hex<br>
2、指定最低波特率、最高波特率和通信端口<br>
  ./stcflash.py xxx.hex --port COM3 --lowbaud 2400 --highbaud 460800<br>
3、其他命令可以参考https://github.com/laborer/stcflash 的README.md
  # 注意事项
  1、对于STC8系列和STC15系列，如果没有指定最低波特率和最高波特率，默认最低波特率为2400，最高波特率为115200;<br>
  2、最低波特率建议使用默认2400，以便单片机的正常检测;<br>
  3、对于STC8系列和STC15系列，最高波特率虽然可以指定1200-460800的任意数字，但为了增加下载的成功率，建议按照固定波特率设置，常见波特率如下：<br>
  460800、230400、115200、57600、38400、28800、19200、14400、9600、4800、2400、1200<br>
  4、对于STC15系列，最高波特率不宜设置过低（建议不小于115200），否则可能出现下载失败情况。因为STC15系列型号较多，握手协议有差别，没法做到全波特率兼容;<br>
  5、本人测试的单片机有STC89C52、STC15W4K48S4、STC15L2K08S2和STC8A8K64S4A12，由于样本实在太稀少，所以不能保证全部型号都能正常识别下载;<br>
  6、单片机的型号是通过特殊的手段诱骗STC-ISP(V6.87H)得到的，把这些型号整合到代码中也是比较繁琐的，纯粹是体力劳动。我在原先的代码当中添加了新的键来映射新添加的型号，详细可以查看代码。如果后面STC再出新型号，如果协议不一样，还是需要做兼容，方法也是类似;<br>
  7、如果有任何意见和建议，欢迎提出，共同探讨！

