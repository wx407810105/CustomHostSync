# CustomHostSync
本项目fork的Clov614的SteamHostSync。基于修改Source.yaml提供自用hosts。

## 1. 实现
对Hosts进行一个新的更  
解决Steam、github访问问题

## 2. 使用方法
## 自动方法(使用工具)
推荐使用Hosts管理工具[SwitchHosts](https://github.com/oldj/SwitchHosts) 
[SwitchHosts备用下载源](https://nas.iaimi.info/s/nT5pb8jMQp32QwB)
### 开机自启动SwitchHosts
win + R 后执行 `shell:startup`    
![](/img/1.png)  
将快捷方式复制进去即可  
![](/img/2.png)  
### 配置SwitchHosts实现自动更新  
下列为fork的Clov614的hosts同步可选的URL有:
如果访问不到GitHub可以尝试将`github.com`替换为`hub.fastgit.xyz`(国内镜像)
1. ALL: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts`  
2. Steam: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts_steam`  
3. github: `https://raw.githubusercontent.com/Clov614/SteamHostSync/main/Hosts_github`    
`镜像地址:`
4. All: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts`  
5. Steam: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts_steam`  
6. github: `https://raw.sevencdn.com/Clov614/SteamHostSync/main/Hosts_github`  

![](/img/3.png)

## 手动方式
#### 1. hosts 文件在每个系统的位置不一，详情如下:
- Windows 系统：`C:\Windows\System32\drivers\etc\hosts`
- Linux 系统：`/etc/hosts`
- Mac（苹果电脑）系统：`/etc/hosts`

#### 2. 修改方法
复制下面的内容至hosts尾部(追加在文本末尾)

```
#github Start
140.82.112.26			alive.github.com
140.82.112.26			live.github.com
185.199.108.154			github.githubassets.com
140.82.114.21			central.github.com
185.199.110.133			desktop.githubusercontent.com
####			assets-cdn.github.com
185.199.111.133			camo.githubusercontent.com
185.199.109.133			github.map.fastly.net
151.101.1.194			github.global.ssl.fastly.net
140.82.112.3			gist.github.com
185.199.111.153			github.io
140.82.113.4			github.com
192.0.66.2			github.blog
140.82.112.5			api.github.com
185.199.109.133			raw.githubusercontent.com
185.199.109.133			user-images.githubusercontent.com
185.199.111.133			favicons.githubusercontent.com
185.199.108.133			avatars5.githubusercontent.com
185.199.110.133			avatars4.githubusercontent.com
185.199.109.133			avatars3.githubusercontent.com
185.199.110.133			avatars2.githubusercontent.com
185.199.108.133			avatars1.githubusercontent.com
185.199.110.133			avatars0.githubusercontent.com
185.199.111.133			avatars.githubusercontent.com
140.82.114.9			codeload.github.com
3.5.17.191			github-cloud.s3.amazonaws.com
16.182.66.25			github-com.s3.amazonaws.com
3.5.2.206			github-production-release-asset-2e65be.s3.amazonaws.com
54.231.161.121			github-production-user-asset-6210df.s3.amazonaws.com
52.216.36.153			github-production-repository-file-5c1aeb.s3.amazonaws.com
185.199.109.153			githubstatus.com
140.82.114.17			github.community
52.224.38.193			github.dev
185.199.109.133			media.githubusercontent.com
#github End
# Last Update Time : 2025-07-26 20:42:23 

#steam Start
23.11.10.111			steamcommunity.com
23.2.133.147			www.steamcommunity.com
23.209.61.185			store.steampowered.com
23.11.10.111			api.steampowered.com
23.11.10.111			help.steampowered.com
23.33.29.17			store.akamai.steamstatic.com
23.220.246.181			steamcdn-a.akamaihd.net
23.33.29.19			cdn.akamai.steamstatic.com
23.2.133.147			steam-chat.com
23.33.29.11			community.akamai.steamstatic.com
#steam End
# Last Update Time : 2025-07-26 20:42:24 

#docker Start
23.185.0.4			docker.com
44.208.254.194			auth.docker.io
44.221.207.111			hub.docker.com
3.161.242.90			docs.docker.com
104.17.35.21			login.docker.com
98.85.153.80			registry.hub.docker.com
104.16.98.215			production.cloudflare.docker.com
52.206.52.86			docker.io
3.94.224.37			registry-1.docker.io
44.208.254.194			index.docker.io
#docker End
# Last Update Time : 2025-07-26 20:42:24 

#cloudflare_jsdelivr Start
104.16.133.229			cloudflare.com
104.18.95.41			challenges.cloudflare.com
151.101.129.229			jsdelivr.map.fastly.net
151.101.1.229			fastly.jsdelivr.net
#cloudflare_jsdelivr End
# Last Update Time : 2025-07-26 20:42:24 

#Github: https://github.com/Clov614/SteamHostSync

```

## 激活生效
大部分情况下是直接生效，如未生效可尝试下面的办法，刷新 DNS：
1. Windows：在 CMD 窗口输入：`ipconfig /flushdns`
2. Linux 命令：`sudo nscd restart`
3. Mac 命令：`sudo killall -HUP mDNSResponder`  

## 手动配置Source.yaml文件添加新hosts  
手动下载可执行文件第一次执行后会在目录生成Source.yaml文件，可手动配置。  

```
ua : Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/100.0.4896.127 Safari/537.36
platforms:
  -
    #github :
    - github            #数组的第一个值为对应平台
    - alive.github.com  #后续值为需要解析ip地址的域名
    - live.github.com
    - github.githubassets.com
    - central.github.com
    - desktop.githubusercontent.com
    - assets-cdn.github.com
    - camo.githubusercontent.com
    - github.map.fastly.net
    - github.global.ssl.fastly.net
    - gist.github.com
    - github.io
    - github.com
    - github.blog
    - api.github.com
    - raw.githubusercontent.com
    - user-images.githubusercontent.com
    - favicons.githubusercontent.com
    - avatars5.githubusercontent.com
    - avatars4.githubusercontent.com
    - avatars3.githubusercontent.com
    - avatars2.githubusercontent.com
    - avatars1.githubusercontent.com
    - avatars0.githubusercontent.com
    - avatars.githubusercontent.com
    - codeload.github.com
    - github-cloud.s3.amazonaws.com
    - github-com.s3.amazonaws.com
    - github-production-release-asset-2e65be.s3.amazonaws.com
    - github-production-user-asset-6210df.s3.amazonaws.com
    - github-production-repository-file-5c1aeb.s3.amazonaws.com
    - githubstatus.com
    - github.community
    - github.dev
    - media.githubusercontent.com
  -
    #steam:
    - steam
    - steamcommunity.com
    - www.steamcommunity.com
    - store.steampowered.com
    - api.steampowered.com
    - help.steampowered.com
    - store.akamai.steamstatic.com
    - steamcdn-a.akamaihd.net
    - cdn.akamai.steamstatic.com
    - steam-chat.com
    - community.akamai.steamstatic.com
```
