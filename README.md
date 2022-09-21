# flowcapter
利用winpcap实现的抓包工具，可以给http接口来访问流量

flowcapture.exe  -m CC-D9-AC-CB-52-AA -a 127.0.0.1 -p 90 -i  5

启动参数说明：

-m  后面接网卡的mac地址，在数据包中做过滤使用，不是指定的mac地址， 不计入流量统计

-a   指定http协议来访问程序读取网络流量时监听的网卡， 127.0.0.1代表只允许本机访问，如果是0.0.0.0代表所有IP均可来访问

-p   指定http协议来访问程序读取网络流量时监听的端口号

-i    指定winpcap获取的网卡设备列表中，是第几个网卡，-m指定的mac地址在winpcap获取的列表中是有顺序的，但是代码没法找到其关联关系，所以这里需要手动指定




以上的命令行启动后
就可以使用  
           curl  http://127.0.0.1:90/flow/second  获取实时信息

           curl  http://127.0.0.1:90/flow/minute  获取最近60分钟信息
           
           curl  http://127.0.0.1:90/flow/hour    获取最近24小时信息
           
           curl  http://127.0.0.1:90/flow/day     获取最近30天信息
           
