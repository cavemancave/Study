# Study
学习笔记

arduino 红外遥控
参考
https://blog.csdn.net/xieyan0811/article/details/56011977
的接线图

我买的模块，VCC和GND交叉了，最后的管脚VCC在最中间

将管脚修改为
int RECV_PIN = 11;        //定义红外接收器的引脚为11 
 int RECV_VCC_PIN = 10;        //定义红外接收器的引脚为11  
int RECV_GND_PIN = 9;        //定义红外接收器的引脚为11 
SetUp修改为
void setup()  
{  
  pinMode(RECV_VCC_PIN,OUTPUT); 
  digitalWrite(RECV_VCC_PIN,HIGH);
  pinMode(RECV_GND_PIN,OUTPUT); 
  digitalWrite(RECV_GND_PIN,LOW);
  
  Serial.begin(9600);  
  irrecv.enableIRIn(); // 启动接收器  
}  



参考
http://www.51hei.com/bbs/dpj-81138-1.html
使用NEC解码模式,
修改IRremote.h
#define DEBUG  1

调试后修改
并修改IRremoteInt.h
#define MARK_EXCESS    50

获得科龙遥控器键值表
开关 C16020C9  C160A029
上   C16008C9
下 C16000C9
模式 C1608029  自动C160849A 制冷C1600051 除湿C16000D1 送风C1608031 制热C160001A
睡眠C160D01A C160001A 去除定时后 C160D00A C160000A

强力 C1608029
左右风 C1608029
定时 C1608039







