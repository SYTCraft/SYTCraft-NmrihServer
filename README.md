# SYTCraft-NmrihServer
盛月堂地狱已满服务器
# 开始
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
