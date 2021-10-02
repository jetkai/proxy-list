<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=for-the-badge
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=for-the-badge
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=for-the-badge
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=for-the-badge
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=for-the-badge
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=for-the-badge
[commit-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Contributors][contributors-shield]][contributors-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

## About This Project & The Proxies
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT** & **CSV** format. 

### Testing:

These proxies are tested ~12x/day (every 2 hours) against OVH & other EU/US hosting providers, they have been verified to write & read data <**AT THE TIME OF TESTING**>. No authentication is required to connect to these proxies.

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = 3000
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort))
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket)
    }
```

### Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

### Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

### ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies.csv)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.csv)

### Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [October 02 2021 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3620
   - **SOCKS5** -> 264
   - **HTTP** -> 1754
   - **HTTPS** -> 1378

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 7016
   - **Unique Online Proxies** -> 6327
   - **Unique Online/Offline Proxies (Archive)** -> 57246

## [SOCKS4 (3620/6327)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.0.136.183:4145
1.0.152.157:4145
1.9.71.4:4153
1.9.167.35:60489
1.9.167.36:60489
1.20.95.95:5678
1.20.99.41:5678
1.20.137.82:32241
1.20.207.200:4145
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.55.241.4:4145
1.71.133.58:5678
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.172.45:31225
1.179.181.213:30500
1.179.183.73:61468
1.179.186.70:1080
1.179.201.189:5678
1.186.40.177:39651
1.186.139.9:39651
1.212.181.131:4145
2.38.199.61:1080
2.139.162.80:4145
3.141.13.98:5678
```

## [SOCKS5 (264/6327)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.61.53.57:9100
5.105.0.135:16379
5.105.1.86:16379
8.129.25.203:9999
8.210.163.246:50016
8.210.163.246:8852
8.210.163.246:50007
8.210.251.244:24691
8.214.2.182:7890
13.250.172.147:48540
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.85:6667
27.116.51.92:6667
27.116.51.119:6667
27.116.51.178:6667
27.116.51.181:6667
27.116.51.186:6667
36.89.86.49:56845
36.94.126.50:1080
37.156.104.178:3327
39.105.134.60:10705
39.108.227.141:1080
43.128.13.103:28010
43.132.157.62:2120
43.224.8.12:6667
43.224.10.8:6667
43.224.10.13:6667
43.224.10.26:6667
```

## [HTTP (1754/6327)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.2.252.65:8080
1.4.157.35:46944
1.10.141.220:54620
1.10.188.78:45208
1.20.99.122:8080
1.20.166.142:8080
1.20.207.200:8080
1.20.217.52:8080
1.32.59.217:47045
1.179.148.9:55636
1.179.217.210:8080
2.59.76.233:53281
2.179.193.146:80
5.16.0.180:8080
5.16.0.186:8080
5.34.153.142:8080
5.130.90.3:8080
5.133.27.61:3129
5.160.101.170:3128
5.183.234.1:8080
8.129.10.162:3228
8.208.91.118:8000
8.208.91.118:80
8.208.91.118:8080
8.208.91.118:3128
8.208.91.118:8008
8.208.91.118:8888
8.242.215.250:999
12.229.217.226:55443
13.229.47.250:8118
```

## [HTTPS (1378/6327)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.4.157.35:46944
1.15.182.239:7890
1.15.228.75:8118
1.20.99.122:8080
1.20.217.52:8080
1.116.155.200:7788
1.179.217.210:8080
2.188.166.22:3128
3.82.92.51:49205
3.82.128.23:49205
3.82.186.15:49205
3.84.17.68:49205
3.86.23.10:49205
3.86.147.133:49205
3.92.48.99:49205
3.95.161.236:49205
3.135.233.222:49205
3.142.122.90:49205
3.143.211.41:49205
5.44.54.16:8080
5.44.54.106:8080
5.59.136.230:8080
5.130.90.3:8080
5.141.244.28:8080
5.183.234.1:8080
8.129.10.162:3228
8.129.179.234:3228
```

## [ARCHIVE (6327/57246)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.136.183:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.152.157:4145
1.0.160.160:4145
1.0.202.54:5678
1.0.205.87:8080
1.0.209.45:4145
1.0.212.209:4145
1.0.213.150:5678
1.0.215.76:5678
1.0.215.239:5678
1.0.225.117:5678
1.0.251.164:4145
1.1.154.73:4145
1.1.160.205:4145
1.1.161.198:4145
1.1.185.208:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
```



Thx Co Pure Gs - Sort Meister! 💟