# 基本配置

通常01dun的默认策略已经适合大多数网站。唯一需要注意的是“SSL/TLS加密模式”

### SSL/TLS加密模式

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

在左侧菜单中点击 “SSL/TLS” - “概述”

右侧可以设置您的SSL/TLS加密模式：

* 如果您的网站服务器上配置了SSL证书，可以通过https直接访问，请选择 “全程”
* 如果您的网站服务器上没有配置SSL证书，请选择“半程“
* 如果您希望完全禁用https访问，可以选择”关闭“。（通常不建议选择此选项，除非您非常清楚自己在做什么。）

{% hint style="info" %}
不管您选择“全程”还是“半程”，只会影响01dun节点与您网站服务器之间的传输方式。不会影响访客访问您的网站的方式。

但如果选择“关闭”，则会导致访客也无法通过https访问您的网站。这种情况下很多浏览器会显示您的网站“不安全”比如：\
![](<../.gitbook/assets/image (3).png>)
{% endhint %}

### 始终使用https

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

在左侧菜单中点击 “SSL/TLS” - “设置”

右侧启用“始终使用HTTPS”的开关。

{% hint style="info" %}
此开关开启时，如果访客访问：http://www.example.com，CDN会发送301跳转响应，让浏览器重定向至：https://www.example.com。避免浏览器显示“不安全”的警告。

通常建议开启。
{% endhint %}

### WebSocket支持

如果您的站点需要使用websocket协议，可以启用 “网络” - “WebSocket” 的开关

### 设置文件最大上传大小

如果您的站点有上传文件的需求，可以到“网络” - “文件最大上传大小” 调整上传大小限制。此限制针对单个请求而言。单位：兆字节。

为减少攻击面，通常建议根据实际情况按需设置，不要设置的过大。
