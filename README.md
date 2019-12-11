## Summary
```
fork自https://github.com/mgsky1/DDNS 
稍微修改了点儿 
利用Python和阿里云云解析API实现。可利用于家庭环境，向公网映射NAS，DB，Web等应用
```

## Install

```bash
pip3 install aliyun-python-sdk-core
```

## Run
```bash
python3 src/DDNS.py      # 默认ipv4
python3 src/DDNS.py -6   # 改用ipv6
```


## Note
> * 基于：Python 3 、阿里云Python SDK、阿里云云解析API
> * 直接运行DDNS.py文件的main函数即可，其他的py文件的main函数都为测试
> * 可将此脚本设置为系统定时任务，例如每天凌晨4:30执行一次或者每次联网时自动执行一次,已经写成ddns.sh 修改脚本路径即可
> * *在最新的[dev](https://github.com/mgsky1/DDNS/tree/dev)分支中增加了同一IP同时绑定多个域名的功能，欢迎体验*
> * 此脚本为DDNS实现的个人想法

## Restrict
> 本脚本适用于家庭宽带IP为动态IP的情形，若不是，可以利用[frp](https://github.com/fatedier/frp)等NAT-DDNS内网穿透工具
## Configuration
本项目修改为使用配置文件方式存储用户配置，配置文件为JSON格式，存放于config.json文件中，形式如下：
```
{
    "AccessKeyId": "Your_AccessKeyId",//你的阿里云AccessKeyId
    "AccessKeySecret": "Your_AccessKeySecret",//你的阿里云AccessKeySecret
    "First-level-domain": "Your_First-level-domain",//一级域名，例如 example.com
    "Second-level-domain": "Your_Second-level-domain"//二级域名，例如 ddns.example.com 填入ddns即可
}
```
## Tip
> 判断自家宽带是否是动态IP的方式：
> * Step 1：百度搜索IP，查到自己的IP地址
> * Step 2：接着本地开一个网站，比如在Windows下直接启动IIS，Linux下安装一个Apache或者Nginx启动，使用它们的默认页面
> * Step 3：然后在路由器上设置好转发规则，公网IP的网络访问端口最好不要用80，80端口可能被运营商封了
> * Step 4：最后利用前面查到的公网IP+端口号访问一下，看看能不能显示内网上的页面，如果可以，恭喜你！
## ScreenShots

注：因为我已经更新过了，所以它提示IP地址已存在，阿里云是不允许同一个IP重复更新的。第二张图为本地，第三张图为外网<br/>
![](https://tva1.sinaimg.cn/large/006tNbRwgy1g9t4cvp3hpj30ja04kt9j.jpg)

![](https://tva1.sinaimg.cn/large/006tNbRwgy1g9t49q2g7uj31ux0u0gs5.jpg)

![](https://tva1.sinaimg.cn/large/006tNbRwgy1g9t4aqvzpmj31g60b6dgt.jpg)

![](https://tva1.sinaimg.cn/large/006tNbRwgy1g9t4b6i337j31z20r2agf.jpg)


## Contribution
如果感兴趣欢迎fork项目，如果有任何问题欢迎在issue区提问~

