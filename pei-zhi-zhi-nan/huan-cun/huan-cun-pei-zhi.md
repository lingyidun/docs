# 缓存配置

针对缓存的全局设置

### 清除缓存

* 清除全部内容：\
  清除01dun CDN节点上的所有缓存资源并重新建立缓存。如果正处于流量高峰期，可能会导致您的源站服务器带宽和系统资源暂时增加。
* 自定义清除：\
  提供一个URL列表，01Dun CDN节点将会清除列表中所有资源的缓存副本。

### 开发模式

启用开发模式会临时禁用缓存4小时，所有请求全部回源。4小时后自动关闭。

{% hint style="info" %}
开发模式有什么用？

_由于缓存的存在，当您更新网站内容时（比如修改了一幅图片、一段CSS样式表或一些javascript代码）并不能立即看到更改，通常要等缓存到期，触发自动刷新才能生效。_

_但如果短时间频繁对网站进行调整和测试，就会显得非常繁琐。此时可以启用开发模式。_

_“开发模式”会禁用缓存功能，让所有的请求绕过缓存从源站获取最新的响应，以便您能够立即看到对网站的更改。请注意：_

_1、此模式开启后，默认持续4小时，4小时后自动关闭。_

_2、开发模式结束后，默认不会清除缓存，如有需要，请手动清理缓存，路径是：缓存-配置-清除全部内容。_

_3、由于所有请求都会绕过缓存，请不要在高峰时段启用此功能。更不要在被攻击的时候启用此功能！_
{% endhint %}

### 缓存级别

配置如何缓存您的站点资源。

* **无查询字符串：**\
  当请求URL中不包含查询字符串，才会被缓存。比如：\
  `https://www.example.com/image.jpg` 会被缓存，因为不包含查询字符串\
  `https://www.example.com/image.jpg?agr=val` 不会被缓存，因为包含了查询字符串
* **忽略查询字符串：**\
  不管请求URL中是否包含查询字符串，都会被缓存,并且被视为同一资源。比如：\
  `https://www.example.com/image.jpg`和`https://www.example.com/image.jpg?agr=val`\
  将会被无差别缓存。对于这两个请求，会返回相同的缓存副本。
* **标准：**\
  对不同的查询字符串分别缓存不同的副本。比如：\
  `https://www.example.com/image.jpg`和`https://www.example.com/image.jpg?agr=val`\
  由于它们携带的参数不同，将会当作两个不同的资源被缓存。对于这两个请求，会返回不同的缓存副本。

### 后台异步更新缓存

允许01Dun节点在更新缓存期间向访问者提供过期的缓存资源。请求不会因为等待源站服务器的响应而延迟，从而提高用户体验。

{% hint style="info" %}
**工作原理:**\
当访问请求到达 01Dun 节点时，请求的资源在缓存中存在但已过期， 01Dun 需要联系源站服务器检查缓存资源是否已更新，这会导致请求因等待源站服务器的响应而产生延迟。\
打开此开关后，01Dun 节点会立即从缓存中返回这个过期的资源给用户，减少响应时间。同时，在后台向源站服务器发送请求，更新过期的缓存内容。\
当新的响应从源站服务器返回后， 01Dun 节点更新缓存中的内容，以供后续请求使用。
{% endhint %}

### 启用永远在线

当源站服务器无法正常响应请求时（例如，由于超时、错误、无法连接等原因），此选项允许 01Dun节点 提供之前缓存的内容，即使这些内容已经过期。这对于维持站点的高可用性和响应性非常有用，尤其是在源站服务不可用或过载的情况下。

### 浏览器缓存 TTL

用于设置访问者的浏览器缓存资源的时长，从而实现网页 “秒开” 的效果。在此期间，浏览器会从其本地缓存中加载文件，从而提高页面加载速度。当这个时间到期后，浏览器将会尝试从 01Dun 节点获取最新的资源。
