# 概览

概览页面是您进入 “站点仪表盘” 后首先看到的页面，展示了您的站点最近24小时、最近7天、最近30天的访问概况。以及一些快速操作和其它信息。

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### 总访客数

展示了单位时间内网站访客的数量

### 总请求数

展示了单位时间内所有访客访问网站时发起的请求数

### 已缓存流量

展示了单位时间内CDN节点从缓存中直接发送给访客的流量，这些流量通常就是CDN为您节省的流量。

### 总流量

展示了单位时间内所有访客产生的总流量。包括CDN从缓存中发送的流量和源站服务器原始流量。

### 缓存命中率

衡量单位时间内缓存命中次数与总请求次数的比值。值越高，意味着源站服务器的负担就越轻。

### 时间范围

默认展示最近24小时的概况。以小时为单位。\
也可以切换到7天、30天来查看最近7天或最近30天的概况，此时统计数据以天为单位。

### 快速操作

* 开发模式：启用开发模式会临时禁用缓存4小时，所有请求全部回源。4小时后自动关闭。

{% hint style="info" %}
开发模式有什么用？

_由于缓存的存在，当您更新网站内容时（比如修改了一幅图片、一段CSS样式表或一些javascript代码）并不能立即看到更改，通常要等缓存到期，触发自动刷新才能生效。_

_但如果短时间频繁对网站进行调整和测试，就会显得非常繁琐。此时可以启用开发模式。_

_“开发模式”会禁用缓存功能，让所有的请求绕过缓存从源站获取最新的响应，以便您能够立即看到对网站的更改。请注意：_

_1、此模式开启后，默认持续4小时，4小时后自动关闭。_

_2、开发模式结束后，默认不会清除缓存，如有需要，请手动清理缓存，路径是：缓存-配置-清除全部内容。_

_3、由于所有请求都会绕过缓存，请不要在高峰时段启用此功能。更不要在被攻击的时候启用此功能！_
{% endhint %}

* 防护级别：调整防火墙的防护级别，包含“完全关闭”、“低”、“中”、“高”、“我正被攻击！”五个级别。\
  通常建议选择“中”，如果误拦截较多，可适当降低防护级别。\
  如果攻击较为频繁，可调整到“高”\
  “我正被攻击！”会强制开启5秒盾，每个访客第一次访问网站，都会展示5秒盾页面，对访问的合法性进行检查。这个级别建议作为被攻击时的最后手段。通常不建议开启。

### 版本信息

展示当前版本、到期时间等信息
