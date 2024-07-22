# 源站内容优化

可以优化网站内容，提升网站加载速度。

### 启用内容压缩

01dun CDN可以使用gzip对传输的数据进行压缩，以加快网站访问速度。还可以自定义针对哪些类型的文件启用压缩。

### 压缩的文件类型

* 纯文本\
  对MIME类型为 text/plain 的资源进行压缩
* javascript\
  对MIME类型为 application/javascript application/x-javascript text/javascript 的资源进行压缩
* CSS\
  对MIME类型为 text/css 的资源进行压缩
* XML\
  对MIME类型为 application/xml 的资源进行压缩

### 压缩等级

可选项包含：“轻微压缩”、“中度压缩”、“强力压缩”。默认为“中度压缩”，兼顾性能与压缩效果。

### 禁用旧版本浏览器的压缩功能

对于某些旧版本的浏览器（比如早期的IE浏览器），禁用压缩功能。这些浏览器通常不支持文件压缩或对压缩功能支持不完善。

