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

# [SAMPLE PROXIES] - [October 01 2021 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 4131
   - **SOCKS5** -> 209
   - **HTTP** -> 1593
   - **HTTPS** -> 1161

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 7094
   - **Unique Online Proxies** -> 6459
   - **Unique Online/Offline Proxies (Archive)** -> 55305

## [SOCKS4 (4131/6459)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.4.214.148:5678
1.6.216.46:9999
1.9.71.4:4153
1.9.167.35:60489
1.9.167.36:60489
1.10.140.43:4145
1.10.187.237:5678
1.20.95.95:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.99.41:5678
1.20.168.157:4145
1.20.184.75:4153
1.20.220.79:4145
1.32.59.217:31981
1.53.137.84:4145
1.53.137.164:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.172.45:31225
1.179.186.69:1080
1.179.201.189:5678
1.179.202.33:5678
1.186.40.9:39651
1.186.40.177:39651
```

## [SOCKS5 (209/6459)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.45.73.63:9050
5.56.134.237:45698
8.131.254.15:9999
8.214.2.182:7890
20.52.130.140:16379
24.249.199.12:4145
24.249.199.14:57335
27.116.51.119:6667
27.116.51.186:6667
31.7.232.178:1080
31.128.248.1:1080
31.128.248.2:1080
31.179.192.30:62311
35.201.142.139:10000
41.231.54.69:3000
41.231.54.69:57481
43.224.8.12:6667
43.224.10.23:6667
43.224.10.30:6667
43.224.10.31:6667
43.224.10.36:6667
43.224.10.43:6667
43.224.10.46:6667
44.192.95.151:1080
47.52.191.42:1080
47.105.138.127:8888
47.110.233.7:1080
47.115.149.82:443
47.149.68.132:1080
49.235.230.134:7890
```

## [HTTP (1593/6459)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.4.157.35:46944
1.10.141.220:54620
1.20.99.122:8080
1.20.207.200:8080
1.20.217.52:8080
1.20.217.221:8080
1.116.4.222:7890
1.179.144.41:8080
1.179.183.73:50178
1.179.217.210:8080
2.32.128.70:3128
3.20.236.208:49205
5.11.17.105:8090
5.34.153.142:8080
5.44.54.16:8080
5.44.54.103:8080
5.44.54.106:8080
5.56.134.237:55963
5.133.27.61:3129
5.141.244.28:8080
5.149.219.201:8080
5.183.234.1:8080
8.208.91.118:8800
12.139.210.41:8080
12.139.210.121:8080
14.102.44.1:44047
14.102.152.157:8080
14.160.32.23:8080
14.161.10.191:8080
```

## [HTTPS (1161/6459)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.220.100:8080
1.2.252.65:8080
1.10.187.237:8080
1.20.166.142:8080
1.20.217.52:8080
1.20.217.221:8080
1.116.4.222:7890
1.116.12.21:3228
1.179.183.73:50178
2.32.128.70:3128
5.11.17.105:8090
5.16.0.49:8080
5.16.0.77:1256
5.16.0.97:1256
5.59.136.230:8080
5.130.90.3:8080
5.133.27.61:3129
5.160.91.130:3128
5.164.211.117:8080
5.188.154.149:8080
8.208.91.118:3128
8.242.215.250:999
8.243.120.54:999
12.139.210.41:8080
12.218.209.130:53281
12.229.217.226:55443
14.102.13.161:8080
14.102.44.1:44047
14.160.26.153:8080
14.161.10.191:8080
```

## [ARCHIVE (6459/55305)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.202.54:5678
1.0.205.87:8080
1.0.209.45:4145
1.0.212.209:4145
1.0.213.150:5678
1.0.215.76:5678
1.0.215.239:5678
1.0.225.117:5678
1.0.251.164:4145
1.1.160.205:4145
1.1.185.208:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
1.1.227.203:4145
1.1.229.183:5678
1.1.230.183:5678
1.1.231.200:4145
1.1.245.173:5678
```



Thx Co Pure Gs - Sort Meister! 💟