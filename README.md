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

# [SAMPLE PROXIES] - [October 01 2021 | 05:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3993
   - **SOCKS5** -> 225
   - **HTTP** -> 2148
   - **HTTPS** -> 1901

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 8267
   - **Unique Online Proxies** -> 7080
   - **Unique Online/Offline Proxies (Archive)** -> 55307

## [SOCKS4 (3993/7080)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.4.157.35:36202
1.4.214.148:5678
1.6.216.46:9999
1.9.71.4:4153
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.10.187.237:5678
1.20.95.95:5678
1.20.99.41:5678
1.20.137.82:32241
1.20.227.66:4145
1.32.59.217:31981
1.71.133.58:5678
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.172.45:31225
1.179.173.114:4153
1.179.181.213:30500
1.179.186.68:1080
1.179.201.189:5678
1.179.202.33:5678
1.186.139.9:39651
1.212.157.115:4145
1.212.181.131:4145
1.220.145.45:4145
```

## [SOCKS5 (225/7080)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.116.4.222:7890
5.34.180.128:9050
5.45.73.63:9050
5.56.134.237:45698
5.61.53.57:9503
5.61.53.57:9341
8.129.8.2:9999
8.131.254.15:9999
8.214.2.182:7890
20.52.130.140:16379
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.178:6667
27.116.51.181:6667
31.7.232.178:1080
31.128.248.1:1080
31.179.192.30:62311
36.27.223.70:64312
36.89.86.49:56845
39.103.216.155:7890
39.108.227.141:1080
43.224.8.12:6667
43.224.10.23:6667
43.224.10.43:6667
43.224.10.44:6667
44.192.95.151:1080
45.149.76.42:9051
45.221.76.114:8080
46.0.234.11:5678
```

## [HTTP (2148/7080)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.4.157.35:46944
1.20.99.122:8080
1.20.166.142:8080
1.20.207.200:8080
1.20.217.52:8080
1.32.59.217:47045
1.116.4.222:7890
1.116.12.21:3228
1.179.144.41:8080
1.179.148.9:55636
1.179.183.73:50178
2.32.128.70:3128
2.59.76.233:53281
3.17.148.147:49205
5.11.17.105:8090
5.16.0.49:8080
5.16.0.174:8080
5.20.91.12:60792
5.34.153.142:8080
5.44.54.16:8080
5.44.54.106:8080
5.56.134.237:55963
5.58.33.187:55507
5.59.136.230:8080
5.130.90.3:8080
5.141.244.28:8080
5.160.91.130:3128
```

## [HTTPS (1901/7080)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.189.58:8080
1.4.157.35:46944
1.32.59.217:47045
1.116.4.222:7890
2.32.128.70:3128
2.180.33.122:8083
3.8.23.128:34798
5.56.134.237:55963
5.58.33.187:55507
5.183.71.145:39305
5.188.154.149:8080
8.208.91.118:80
8.208.91.118:8888
8.242.215.250:999
12.139.210.41:8080
14.102.44.25:44047
18.197.97.162:9300
18.197.180.35:9300
18.220.20.81:8080
27.42.168.46:55481
27.116.51.178:6666
27.121.85.74:8080
27.147.219.46:8080
27.191.60.79:3256
27.191.60.85:3256
27.191.60.202:3256
27.191.60.238:3256
27.191.60.242:3256
27.191.60.243:3256
31.128.71.241:8081
```

## [ARCHIVE (7080/55307)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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