# 证书管理

对站点的https证书进行管理

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

### 证书列表

此列表展示了当前部署到01dun CDN 节点上的证书。包含颁发机构、签发者、认证域名、有效期等信息。

### 添加证书

点击页面右下角的“添加证书”按钮，会展开一个新卡片，用来配置证书。

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

1. 在此卡片中，输入证书的主机名，比如www
2. 复制您的密钥key文件内容到 “密钥（KEY）” 文本框
3. 复制您的证书pem文件内容到 “证书（PEM格式）” 文本框
4. 点击提交即可。

{% hint style="info" %}
证书管理权限可能因版本不同而不同。

对于大多数场景，01dun自动管理证书是最佳的选择。
{% endhint %}

