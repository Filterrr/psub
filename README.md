# 原基础上新增优化
并发请求：
优化：使用 Promise.all 并行处理所有订阅源的下载和解析，大幅缩短总耗时。

前端缓存：
优化：使用 Cloudflare Cache API 对前端页面进行缓存，显著提升加载速度并减少 GitHub API 调用。

节点复用映射：
优化：建立 hostMap，对于相同的原始服务器地址，始终映射到同一个随机域名。这不仅减小了 replacements 映射表的大小（降低内存占用），也让生成的订阅更像真实的机场订阅。

超时控制：
优化：为上游订阅的 fetch 请求增加超时控制，防止因为某个源挂死导致整个 Worker 超时（Error 1101）。


# psub
利用CF Worker搭建的反代订阅转换工具，通过随机化服务器地址和节点账号密码，解决用户转换订阅的隐私问题

### 演示网站
https://psub.888005.xyz

### 视频教程
https://youtu.be/X7CC5jrgazo

环境变量名：`BACKEND`

KV或R2变量名：`SUB_BUCKET`

### 支持反代转换的协议
 - shadowsocks
 - shadowsocksR
 - vmess
 - trojan
 - vless(取决于后端)
 - hysteria(取决于后端)

### 打赏
请我喝矿泉水：[全专线中专机场AFF链接](http://b.880805.xyz/)

请我喝桶装水：[搬瓦工美国CN2 GIA线路AFF链接](https://bwg.880805.xyz/)
