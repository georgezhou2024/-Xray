# 一键搭建教程 VPS 梯子




### 一推荐安装 Xray + VLESS + Reality（目前最抗封锁、速度好、兼容性强）。
Bash
```
bash <(curl -Ls https://raw.githubusercontent.com/233boy/Xray/master/install.sh)

```
或者用这个备用：
```
bash <(wget -qO- https://github.com/233boy/Xray/raw/main/install.sh)
```
安装过程中按提示操作即可（默认会自动生成 VLESS + Reality 配置）。
安装完成后，脚本会显示：
• VLESS 链接
• 二维码
• 管理命令

### 二、节点搭建完毕  输入快速查看
```
xary
```
### 三、订阅转换网站 （订阅完毕的链接可以一键复制转换网站）
```
https://acl4ssr-sub.github.io/
```
现在主流系统（Debian 10+/11/12、Ubuntu 18.04/20.04/22.04/24.04、CentOS 8+/Alma/Rocky 等）内核基本都自带 BBR，直接开启即可，不用换内核，风险最低。SSH 登录 VPS 后，复制下面三行命令一次性执行：

```
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
```
验证是否成功执行下面两条命令：

```
sysctl net.ipv4.tcp_congestion_control
lsmod | grep bbr
```
第一条应显示：net.ipv4.tcp_congestion_control = bbr
第二条应出现 tcp_bbr 字样

看到以上结果就说明开启成功了，对梯子（代理）速度会有明显提升，尤其是高延迟、有丢包的线路。



    
### 二 、搭建完后，放行端口
    iptables -I INPUT -p tcp --dport 42890 -j ACCEPT
    iptables -I INPUT -p tcp --dport 443 -j ACCEPT
    iptables -I INPUT -p tcp --dport 80 -j ACCEPT
    iptables -I INPUT -p tcp --dport 90 -j ACCEPT
    iptables -I INPUT -p tcp --dport 9090 -j ACCEPT
    iptables -I INPUT -p tcp --dport 8388 -j ACCEPT

