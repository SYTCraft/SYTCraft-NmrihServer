# SYTCraft-NmrihServer
盛月堂地狱已满服务器
# 开始
### 注意事项
###### 安装前，请确认服务器系统为 Centos 7+
###### 请严格按照过程执行命令，否则容易出现错误
###### 如忽视安全问题，可跳过新建用户
### 新建用户
###### 新建用户
    useradd -m steam
###### 切换用户
    su steam
### 获取依赖
    yum install glibc libstdc++
    yum install glibc.i686 libstdc++.i686
### 获取 SteamCMD
###### 创建 SteamCMD 运行目录
    mkdir /home/steam/steamCMD
###### 下载 SteamCMD
    wget -P /home/steam/steamCMD http://media.steampowered.com/client/steamcmd_linux.tar.gz
###### 解压 SteamCMD
    tar -xvzf /home/steam/steamCMD/steamcmd_linux.tar.gz -C /home/steam/steamCMD
### 获取服务端
###### 创建服务端运行目录
    mkdir /home/steam/serverfiles/nmrih
###### 下载服务端
    /home/steam/steamCMD/steamcmd.sh +force_install_dir "/home/steam/serverfiles/nmrih" +login anonymous +app_update 317670 validate +quit
### 运行服务端
###### 方案一、
    cd /home/steam/serverfiles/nmrih
    ./srcds_run -game nmrih +map nmo_suzhou -maxplayers 9
###### 方案二、
    /home/steam/serverfiles/nmrih/srcds_run -game nmrih +map nmo_suzhou -maxplayers 9
