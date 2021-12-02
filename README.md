
```

1. 安装
    wget https://github.com/cccttttt/open-pool/releases/download/open-pool-v1.0/incomerate-server.zip
    
    unzip incomerate-server.zip
    chmod 777 incomerate-server
    
    接下来生成ssl 证书文件server.crt 
    并配置config.json文件

2. 配置服务器
    server SSL证书生成
    生成server.key :
        openssl ecparam -genkey -name secp384r1 -out server.key
    生成server.crt:
    openssl req -new -x509 -sha256 -key server.key -out server.crt -days 3650
    
    编辑矿池配置文件：config.json
    详见config.json example
    
    ethminer: asia2.ethermine.org
    币印ETH：ryj.s.eksy.org:443
    
    
```

    

```
config.json example:

   {
        "listen": "0.0.0.0:6666",  // 中转服务器监听端口
        "use_ssl": false,  // 如果需要使用ssl加密，改为true 
        "ssl_key": "server.key", 
        "ssl_crt": "server.crt",
        "pool_url": "asia2.ethermine.org:14444",  //中转服务器连接连接的矿池地址，算力将在该矿池显示
        "income_list": [
        //服务器提供者抽水配置，如不需要，可以为空
        {
            "url": "asia2.ethermine.org:14444",  //矿池地址
            "address": "0x51dF1C17f38FEB74CF4f8514Ca6C326d6FBFd491", // 捐赠地址,此处填写服务提供者地址
            "name": "donate",  //
            "rate": 1  // 捐赠比率
        }
        ]
    }
    
```


```
鼓励开发者捐赠地址：
ETH:0x82aad501508693b942372840bebe002a1e6e4c98


```