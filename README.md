# Sub-clash
Hysteria2、Reality 节点转换Clash 配置文件
适配clash Verge、openClash、Stash(不支持Reality)
本地运行转换，绝对安全
# 使用
1、下载脚本
```
curl https://raw.githubusercontent.com/loohalh/Sub-clash/refs/heads/main/sub-clash.sh -o sub-clash.sh && chmod +x sub-clash.sh
```
2、创建节点配置文件
创建文件：local.txt，也可以修改脚本LOCAL_FILE值指定文件
参照example.local.txt模板获取节点对应内容填入，目前只支持Hysteria2和Reality
注意：Stash不支持Reality，需要在Stash客户端使用，请剔除Reality节点

```
#支持多条，一行一个

#Hysteria2 
#1. skip-cert-verify 可不传，默认true
#2. download-bandwidth和upload-bandwidth可不传，默认100
- {name: 🇭🇰 HDY-Hk  | Hy2, type: hysteria2, server: 10.10.10.10, port: 5000, password:xxxxxxxxxxxxxxx, skip-cert-verify: true, sni: www.xxx.com, download-bandwidth: 100, upload-bandwidth: 100}

#Reality
#1. tls 可不传，默认true
#2. client-fingerprint可不传， 默认chrome
#3. network不传， 默认tcp
#4. tfo、skip-cert-verify不传， 默认false
#5. flow可不传，默认xtls-rprx-vision-udp443
- {name: 🇭🇰 HDY-HK  | Re, server: xxx.com, port: 50000, type: vless, uuid: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx, tls: true, client-fingerprint: chrome, servername: www.xxx.com, network: tcp, tfo: false, skip-cert-verify: false, flow: xtls-rprx-vision-udp443, reality-opts: {public-key: xxxxxxxxxxxxxxx_xxxxxxxxxxxxxxxxxxxxxxx, short-id: xxxxxxxxxxx}}
```
3、转换
生成sub-hysteria.yaml，可修改脚本OUTPUT_FILE值，自定义生成文件名称
```
bash sub-clash.sh
#或者
./sub-clash.sh
```
可以把yaml文件上传到cdn或者文件服务器，获取链接，在clash客户端添加订阅使用
