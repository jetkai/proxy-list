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

# [SAMPLE PROXIES] - [September 27 2021 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3484
   - **SOCKS5** -> 150
   - **HTTP** -> 1132
   - **HTTPS** -> 1179

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 5945
   - **Unique Online Proxies** -> 5445
   - **Unique Online/Offline Proxies (Archive)** -> 55233

## [SOCKS4 (3484/5445)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.1.231.200:4145
1.9.167.36:60489
1.10.140.43:4145
1.20.96.30:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.227.66:4145
1.53.137.84:4145
1.53.137.164:4145
1.179.147.5:52210
1.179.148.9:36476
1.179.173.114:4153
1.179.201.189:5678
1.180.133.138:1080
1.186.40.2:39651
1.186.40.9:39651
1.186.40.157:39651
1.186.139.9:39651
1.212.181.131:4145
2.139.162.80:4145
2.183.8.145:4153
2.183.9.228:5678
3.141.13.98:5678
3.144.23.47:5678
5.2.180.254:4145
5.8.190.219:5678
5.22.154.50:32127
5.34.74.214:4145
5.34.74.218:5678
```

## [SOCKS5 (150/5445)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.56.134.237:45698
8.210.163.246:50018
8.210.163.246:50045
24.249.199.12:4145
24.249.199.14:57335
27.29.93.230:7890
27.116.51.85:6667
31.128.248.1:1080
36.89.86.49:56845
41.220.7.131:8080
43.224.8.14:6667
43.224.10.13:6667
43.224.10.26:6667
43.224.10.33:6667
43.224.10.35:6667
43.224.10.36:6667
45.221.76.114:8080
47.75.113.110:10009
47.75.113.110:10010
47.75.113.110:10004
47.105.138.127:8888
47.149.68.132:1080
54.146.75.7:33263
54.146.75.7:5569
62.182.158.27:8000
64.126.160.161:31337
66.42.224.229:41679
66.135.227.178:4145
69.61.200.104:36181
70.166.167.36:4145
```

## [HTTP (1132/5445)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.10.188.78:45208
1.20.99.122:8080
1.116.4.222:7890
1.116.12.21:3228
1.179.148.9:55636
1.179.217.210:8080
2.32.128.70:3128
2.59.76.233:53281
2.180.33.122:8083
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.26.96.212:8080
5.34.153.142:8080
5.44.54.16:8080
5.56.134.237:55963
5.58.33.187:55507
5.160.91.130:3128
5.164.211.117:8080
8.129.10.162:3228
8.208.91.118:80
8.208.91.118:8000
8.208.91.118:8081
8.208.91.118:8008
8.242.215.250:999
14.161.252.185:55443
14.170.154.10:8080
14.177.235.17:8080
14.192.2.161:83
```

## [HTTPS (1179/5445)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.2.252.65:8080
1.10.188.78:45208
1.20.207.200:8080
1.116.4.222:7890
1.179.183.73:50178
2.32.128.70:3128
2.180.33.122:8083
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.44.54.16:8080
5.44.54.103:8080
5.44.54.106:8080
5.56.134.237:55963
5.59.136.230:8080
5.133.27.61:3129
5.149.219.201:8080
5.160.91.130:3128
5.164.211.117:8080
8.129.10.162:3228
8.208.91.118:81
8.208.91.118:3128
8.208.91.118:8081
8.208.91.118:8888
8.243.138.218:999
14.102.13.161:8080
14.139.57.195:23500
14.161.10.191:8080
14.177.236.212:55443
14.192.2.161:83
```

## [ARCHIVE (5445/55233)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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