# Dify - Zmicro Service

## Getting Started

### Installation

- Step 1: Run script
  
```bash
curl https://raw.githubusercontent.com/zmicro-design/service-dify/master/install -o /tmp/install.sh && bash /tmp/install.sh && rm /tmp/install.sh
```

- Step 2: Input your login password

```
✖ [2024-05-09 22:24:53][service] service(dify) not found
ℹ [2024-05-09 22:24:53][service] try to install service(dify) ...
ℹ [2024-05-09 22:24:53] start to install service dify ...
ℹ [2024-05-09 22:24:55] succeed to install service dify.
#####################################################
# 更多用法
# 1. 查看日志
$ zmicro service logs dify -f --tail 100
# 2. 修改配置
$ zmicro service edit config dify
# 3. 重启服务
$ zmicro service restart dify
# 4. 升级服务
$ zmicro service upgrade dify
# 5. 关闭服务
$ zmicro service stop dify
#####################################################

Password:
```

- Step 3: Input or confirm `Port` and `Secret Key` for dify

```
? Port 8080
? Secret Key (default: 5ee73679-b00c-4ec1-8e53-accc12c6cf40)
[+] Running 70/8
 ✔ sandbox 12 layers [⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                           81.1s
 ✔ db 8 layers [⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                                     13.9s
 ✔ dify 5 layers [⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                                      19.0s
 ✔ weaviate 4 layers [⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                                   16.8s
 ✔ worker Pulled                                                                                                                                                     67.3s
 ✔ api 12 layers [⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                               67.3s
 ✔ redis 6 layers [⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                                    78.8s
 ✔ web 15 layers [⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                                                                            61.4s
[+] Running 8/8
 ✔ Container dify-sandbox-1   Started                                                                                                                                 1.2s
 ✔ Container dify-db-1        Started                                                                                                                                 1.2s
 ✔ Container dify-weaviate-1  Started                                                                                                                                 1.2s
 ✔ Container dify-web-1       Started                                                                                                                                 1.2s
 ✔ Container dify-redis-1     Started                                                                                                                                 1.2s
 ✔ Container dify-worker-1    Started                                                                                                                                 0.0s
 ✔ Container dify-api-1       Started                                                                                                                                 0.0s
 ✔ Container dify-dify-1      Started
```

- Step 4: Open New Terminal, see logs for dify with running `zmicro service logs dify -f --tail 100`

```bash
zmicro service logs dify -f --tail 100
```

- Step 5: Visit Browser: `http://127.0.0.1:8080`

## More Usage

### 1. Start Dify

```bash
zmicro service start dify
```

### 2. Stop Dify

```bash
zmicro service stop dify
```

### 3. See logs

```bash
zmicro service logs dify -f --tail 100
```

### 4. Update Config

```bash
zmicro service edit config dify
```

### 5. Restart Dify

```bash
zmicro service restart dify
```

### 6. Upgrade Dify

```bash
zmicro service upgrade dify
```

## FAQ

- 1. Question: network error like `curl: (7) Failed to connect to raw.githubusercontent.com port 443 after 15 ms: Couldn't connect to server`
  - Answer: apply your proxy in your terminal before install
    - if you proxy service run in port `7890`, like `clash`
      - 1. run command: `export HTTPS_PROXY=http://127.0.0.1:7890 HTTP_PROXY=http://127.0.0.1:7890`
      - 2. run install command again

- 2. Question: show `Password:`
  - Answer: input your login password. docker should use your password.

## License
* MIT
