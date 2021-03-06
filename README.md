# QUPLOAD

一个用 Golang 写的七牛云上传工具。使用七牛云官方的服务端 API 完成。
---

## 安装
`go install github.com/moorper/qupload`

## 使用
```shell
qupload [option] file.png

option:

-k 设置文件上传名称
-p 设置文件上传前缀，会拼接在当前的文件名前边，不能和 -k 命令同时使用
-s 选择文件上传空间，为配置文件的 section
-v 查看版本

```

上传成功返回以下内容
```
key : file.png
url :  http://oph6h5t6t.bkt.clouddn.com/file.png
markdown : ![upload.jpg](http://oph6h5t6t.bkt.clouddn.com/file.png)
```
注：
* MacOS 可直接拖拽图片到控制台获取图片路径

## 配置
第一次运行会自动在 `~/.qupload/qupload.ini` 创建配置文件：
```
[default]	
AccessKey = ***
SecretKey = ***
Bucket = bucket
BucketPublic = true # bool
BucketDomain = http://***
# 可不受限制的添加更多 Section 只需使用 qupload -s=other file.png 即可
# [other]
# AccessKey = ***
# SecretKey = ***
# Bucket = bucket
# BucketPublic = true # bool
# BucketDomain = http://***
```

## TODO
- [ ] 本地记录上传文件
- [ ] 免配置直接上传文件到 [https://sm.ms/](https://sm.ms/)

---

## 版本
### v0.0.1
* 简单配置即可使用 `qupload` 命令上传文件
### v0.0.2
* 修改配置文件路径为 `~/.qupload/qupload.ini`
* 自动创建配置文件
* 支持多帐号配置
### v0.0.3
* 支持修改上传文件名
