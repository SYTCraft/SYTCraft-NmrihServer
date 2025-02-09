# SYTCraft-NmrihServer
盛月堂地狱已满服务器

# 文档导航
### [开始](https://github.com/SYTCraft/SYTCraft-NmrihServer/blob/Master/README.md#%E5%BC%80%E5%A7%8B)
###### [Debian安装指南](https://github.com/SYTCraft/SYTCraft-NmrihServer/blob/Master/README.md#debian%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97-1)
###### [Centos安装指南](https://github.com/SYTCraft/SYTCraft-NmrihServer/blob/Master/README.md#centos%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97-1)

# 开始
###### 运行游戏伺服器前您需要部署 MCSManager Web程式以便于管理伺服器
###### 主控推荐配置：2 H 逻辑核心/4 GiB 运行内存（最低配置：1 H 逻辑核心/512 MiB 运行内存）
###### 被控推荐配置：8 H 逻辑核心/16 GiB 运行内存（最低配置：2 H 逻辑核心/2 GiB 运行内存）
###### MCSManager 主控/被控截至此部署文档更新均为同一Web程式，使用同一安装命令
###### 部署文档 https://docs.mcsmanager.com/zh_cn/
---
#### 快速部署 MCSManager
###### Linux 一键安装
    sudo su -c "wget -qO- https://script.mcsmanager.com/setup_cn.sh | bash"
---
## Debian安装指南
### 注意事项
###### 推荐使用Debian12系统镜像运行游戏伺服器
###### 请严格按照过程执行命令，否则容易出现错误
### 获取依赖
    sudo apt update && sudo apt-get install lib32gcc-s1
### 获取 SteamCMD
###### 创建 SteamCMD 运行目录
    mkdir -p /home/steam/SteamCMD && cd /home/steam/SteamCMD
###### 下载 SteamCMD
    wget https://media.st.dl.bscstorage.net/client/installer/Steamcmd_linux.tar.gz
###### 解压 SteamCMD
    unzip -o steamcmd_linux.tar.gz && cd /home
### 获取服务端
###### 创建服务端运行目录
    mkdir -p /home/steam/ServerFiles/Nmrih && cd /home/steam/Serverfiles/nmrih
###### 下载服务端
    /home/steam/SteamCMD/steamcmd.sh +force_install_dir "/home/steam/Serverfiles/nmrih" +login anonymous +app_update 317670 validate
### 运行服务端
    cd /home/steam/ServerFiles/Nmrih && ./srcds_run -game nmrih +map nmo_suzhou -maxplayers 9

## Centos安装指南
### 注意事项
###### 推荐使用Centos 7.6系统镜像运行游戏伺服器
###### 请严格按照过程执行命令，否则容易出现错误
### 获取依赖
    yum install glibc libstdc++
    yum install glibc.i686 libstdc++.i686
### 获取 SteamCMD
###### 创建 SteamCMD 运行目录
    mkdir /home/steam/SteamCMD && cd /home/steam/SteamCMD
###### 下载 SteamCMD
    wget https://media.st.dl.bscstorage.net/client/installer/steamcmd_linux.tar.gz
###### 解压 SteamCMD
    tar -xvzf steamcmd_linux.tar.gz
### 获取服务端
###### 创建服务端运行目录
    mkdir /home/steam/ServerFiles/Nmrih
###### 下载服务端
    /home/steam/SteamCMD/steamcmd.sh +force_install_dir "/home/steam/ServerFiles/Nmrih" +login anonymous +app_update 317670 validate +quit
### 运行服务端
###### 方案一、
    cd /home/steam/ServerFiles/Nmrih && ./srcds_run -game nmrih +map nmo_suzhou -maxplayers 9
