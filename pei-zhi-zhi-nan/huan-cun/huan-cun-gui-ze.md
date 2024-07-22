# 缓存规则

配置全局的缓存规则和策略

{% hint style="info" %}
缓存规则说明：

默认情况下，01Dun节点将会对源站的200、301、302响应中指定的资源类型进行缓存。但下列情况除外：&#x20;

* 如果源站的响应标头包含了 X-Accel-Expires 字段，则缓存时长以 X-Accel-Expires 为准
* 如果源站的响应标头包含了 Expires、Cache-Control 字段，则缓存时长以 Expires、Cache-Control 为准
* 如果源站的响应标头包含了 Set-Cookie 字段，则不会缓存此响应
* 如果源站的响应标头包含了具有特殊值“ \* ”的 Vary 字段字段，则不会缓存此响应
* 如果源站的响应标头包含具有其他值的 Vary 字段，则将01Dun节点将考虑相应的请求标头字段来缓存此类响应。

可以通过 “强制缓存资源” 选项调整这一行为。
{% endhint %}

### 缓存图像

开启此选项后，将会对以下文件类型进行缓存： BMP、GIF、ICO、JPEG、JPG、PNG、TIF、TIFF、WEBP、SVG、SVGZ

### 缓存音频

开启此选项后，将会对以下文件类型进行缓存： MP3、OGG、WAV、FLAC、MID、MIDI

### 缓存视频

开启此选项后，将会对以下文件类型进行缓存： AVI、MKV、MP4、MOV、MPG、MPEG、WEBM

### 缓存文档

开启此选项后，将会对以下文件类型进行缓存： CSS、JS、DOC、DOCX、PDF、PPT、PPTX、XLS、XLSX、CSV

### 缓存HTML

开启此选项后，将会对以下文件类型进行缓存： HTML、HTM、SHTML

### 缓存其它资源

开启此选项后，将会对以下文件类型进行缓存： 7Z、GZ、RAR、TAR、ZIP、ZST、BZ2、EOT、OTF、TTF、WOFF、WOFF2、APK、DMG、EXE、JAR、BIN、CLASS、DMG、EPS、PICT、PS、SWF

### 节点缓存时间

对于符合缓存规则的资源，指定01dun CDN 节点缓存时长。到期后，01dun会联系源站执行刷新缓存的操作。

### 强制缓存资源

默认情况下，01Dun尊重源站响应标头中的缓存控制指令。如果包含了缓存控制字段，则缓存控制字段比“节点缓存时间”具有更高的优先级，除非开启强制缓存资源。 开启此选项后，将会忽略源站响应标头中的 X-Accel-Expires、Expires、Cache-Control、Set-Cookie、Vary字段，对响应进行缓存。
