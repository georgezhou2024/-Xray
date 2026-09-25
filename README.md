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


    
### 二 、搭建完后，放行端口
    iptables -I INPUT -p tcp --dport 42890 -j ACCEPT
    iptables -I INPUT -p tcp --dport 443 -j ACCEPT
    iptables -I INPUT -p tcp --dport 80 -j ACCEPT
    iptables -I INPUT -p tcp --dport 90 -j ACCEPT
    iptables -I INPUT -p tcp --dport 9090 -j ACCEPT
    iptables -I INPUT -p tcp --dport 8388 -j ACCEPT

