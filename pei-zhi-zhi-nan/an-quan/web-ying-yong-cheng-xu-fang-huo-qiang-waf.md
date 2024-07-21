# Web应用程序防火墙WAF

Web应用程序防火墙 (WAF) 会检测此域名下所有子域名所有流量的请求，并采用定义好的规则。

### IP 黑/白 名单

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

* IP白名单：\
  添加到白名单中的IP，防火墙将不会拦截，无条件放行。\
  默认允许所有IP，所以不需要设置IP白名单。只有当禁止了所有IP，才需要设置IP白名单。
* IP黑名单：\
  添加到黑名单中的IP，防火墙将会拦截。如果要拉黑某个IP，在黑名单中填入相应的IP地址即可。\
  如果要禁止所有IP，可以在IP黑名单中输入`0.0.0.0`，然后再配置IP白名单。

IP地址的填写支持单个IP，如：`192.168.0.1`；也支持CIDR格式（如：`192.168.0.0/24），表示一个IP段。`

如果IP被判定为禁止，将不会再进行后续（比如国家/地区、user-agent）的判断。

### User-Agent 黑/白 名单

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

* **User-Agent 白名单：**\
  **添加到白名单中的User-Agent，**防火墙将不会拦截，无条件放行。\
  默认允许所有User-Agent访问，所以不需要设置User-Agent白名单。只有当禁止了所有User-Agent，才需要设置User-Agent白名单。
* **User-Agent 黑名单：**\
  添加到黑名单中的**User-Agent** ，防火墙将会拦截。如果要拉黑某类**User-Agent** ，在黑名单中填入相应的**User-Agent** 即可。\
  如果要禁止所有**User-Agent** ，可以在**User-Agent** 黑名单中输入\*，然后再配置**User-Agent** 白名单。

User-Agent必须输入完整。\*表示匹配所有。

如果User-Agent被判定为禁止访问，将不会再进行后续（比如国家/地区）判断。

{% hint style="info" %}
由于User-Agent容易被伪造的特性，User-Agent黑白名单通常仅用于拦截一些恶意爬虫或坏机器人，并不适合作为防攻击的缓解措施。
{% endhint %}

### 国家/城市 黑/白 名单

<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

* 国家/省/市 白名单：\
  **添加到白名单中的地区，**防火墙将不会拦截，无条件放行。\
  默认允许所有地区访问，所以不需要设置 国家/省/市 白名单。只有当禁止了所有地区，才需要设置 国家/省/市 白名单。
* 国家/省/市 黑名单：\
  如果要拉黑某个国家、省份、城市，在黑名单中选择相应的国家、省份、城市即可，支持搜索，支持多选。

省份、城市仅支持中国大陆地区。

如果要仅允许特定国家或地区访问，可以在黑名单中选择`所有国家`，然后在白名单中指定允许的国家或地区。

{% hint style="info" %}
截图中的含义是：\
国家级别禁止日本和澳大利亚访问，省级别禁止四川访问，城市级别允许成都访问，禁止安徽黄山访问。
{% endhint %}
