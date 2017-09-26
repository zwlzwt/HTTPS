# HTTPS
## 实现https 用express和node.js
利用openssl生成密钥
## 生成密码钥方法：
* 生成私钥key文件
  openssl genrsa 1024 > /path/to/private.pem

* 通过私钥文件生成CSR证书签名
  openssl req -new -key /path/to/private.pem -out csr.pem

* 通过私钥文件和CSR证书签名生成证书文件
  openssl x509 -req -days 365 -in csr.pem -signkey /path/to/private.pem -out /path/to/file.crt

### 利用node.js和express分别起两个端口服务
1. 6000端口 http
  
2. 6001端口 https 
