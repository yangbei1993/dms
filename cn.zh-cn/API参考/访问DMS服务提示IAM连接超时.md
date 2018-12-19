# 访问DMS服务提示IAM连接超时<a name="zh-cn_topic_0043875984"></a>

## 问题描述<a name="section1296910476388"></a>

访问DMS服务的API报错，提示IAM连接超时，显示如下：

```
Get quota fail: 401
{"message": "Connect IAM Timeout", "request_id": 
"5ACB6B21-DAF6-47C8-B7A4-45A7BDC57FC6"}
```

## 可能原因<a name="section144290562385"></a>

在Web Console删除AK/SK，导致AK/SK无效。

## 处理方法<a name="section1212331917398"></a>

1.  登录管理控制台。
2.  单击用户名，在下拉列表中单击“我的认证”。
3.  单击“管理访问密钥”。
4.  单击“新增访问密钥”，进入“新增访问密钥”页面。
5.  输入登录密码和短信验证码，单击“确定”，下载密钥，请妥善保管。
6.  用新的AK/SK访问DMS服务。

