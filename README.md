BBR安装教程:

BBR可以用来加速网络，旨在增加网络连通率，安装后理论上网速更好。如果不安装也是可以正常使用SSR或者V2Ray的。

sudo yum install wget -y

sudo wget --no-check-certificate https://raw.githubusercontent.com/youchanlee/bbr/master/bbr.sh 

sudo chmod +x bbr.sh

sudo ./bbr.sh

安装完成后系统需要重启，重启后使用命令uname -r来查询系统内核是多少。

如果内核在4.09之上即代表成功。内核安装成功后，使用下面的命令安装BBR，红色的为命令，黑色的为返回值。
命令:

    sysctl net.ipv4.tcp_available_congestion_control

返回值一般为：

net.ipv4.tcp_available_congestion_control = bbr cubic reno
命令:


    sysctl net.ipv4.tcp_congestion_control

返回值一般为：

net.ipv4.tcp_congestion_control = bbr
命令:

    sysctl net.core.default_qdisc

返回值一般为：

net.core.default_qdisc = fq
命令:

    lsmod | grep bbr

返回值有 tcp_bbr 模块即说明 bbr 已启动。

