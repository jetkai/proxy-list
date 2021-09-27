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

# [SAMPLE PROXIES] - [September 27 2021 | 01:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 6517
   - **SOCKS5** -> 496
   - **HTTP** -> 1361
   - **HTTPS** -> 1392

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 9766
   - **Unique Online Proxies** -> 8831
   - **Unique Online/Offline Proxies (Archive)** -> 8831

## [SOCKS4 (6517/8831)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.1.231.200:4145
1.2.202.165:4145
1.4.157.35:36202
1.4.168.12:4145
1.4.214.148:5678
1.9.71.4:4153
1.9.165.67:4153
1.10.140.43:4145
1.10.187.237:5678
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.96.156:4153
1.20.96.164:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.184.75:4153
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.71.133.58:5678
1.179.130.201:4153
1.179.145.101:33109
1.179.147.5:52210
1.179.172.45:31225
1.179.173.114:4153
1.179.181.213:30500
1.179.183.73:61468
1.179.186.68:1080
```

## [SOCKS5 (496/8831)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.116.4.222:7890
5.34.180.128:9050
5.45.73.63:9050
5.56.134.237:45698
5.61.53.57:9211
5.61.53.57:9052
5.61.53.57:9053
5.61.53.57:9090
5.61.53.57:9341
5.61.53.57:9300
5.164.23.101:1080
5.167.53.191:9999
8.131.254.15:9999
8.210.163.246:50001
8.210.163.246:50011
8.210.163.246:50024
8.210.163.246:50004
8.210.163.246:50032
8.210.163.246:50044
8.210.163.246:50009
8.210.163.246:8852
8.210.163.246:50050
8.210.163.246:50041
8.210.163.246:50018
8.210.163.246:50048
8.210.163.246:50008
8.210.163.246:50043
8.210.163.246:50002
8.210.163.246:50025
8.210.163.246:50007
```

## [HTTP (1361/8831)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.2.252.65:8080
1.10.188.78:45208
1.20.99.122:8080
1.20.166.142:8080
1.116.4.222:7890
1.179.144.41:8080
1.179.217.210:8080
2.32.128.70:3128
2.180.33.122:8083
5.11.17.105:8090
5.16.0.180:8080
5.44.54.16:8080
5.44.54.106:8080
5.149.219.201:8080
5.183.234.1:8080
8.129.10.162:3228
8.129.179.234:3228
8.208.91.118:8081
8.211.241.7:1088
8.214.2.182:7890
8.242.215.250:999
8.243.138.218:999
12.139.210.121:8080
14.102.44.1:44047
14.161.10.191:8080
14.170.154.10:8080
14.177.235.17:8080
14.207.57.244:8080
14.241.225.167:80
```

## [HTTPS (1392/8831)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.10.141.220:54620
1.10.188.78:45208
1.20.99.122:8080
1.116.4.222:7890
1.116.12.21:3228
1.179.144.41:8080
1.179.217.210:8080
2.32.128.70:3128
2.180.33.122:8083
5.16.0.180:8080
5.20.91.12:60792
5.133.27.61:3129
5.141.244.28:8080
5.164.211.117:8080
8.129.179.234:3228
8.208.82.169:1088
8.208.91.118:80
8.208.91.118:81
8.208.91.118:8888
8.208.91.118:8080
8.208.91.118:3128
8.208.91.118:8081
8.208.91.118:8000
12.139.210.121:8080
12.218.209.130:53281
13.229.47.250:8118
14.102.13.161:8080
14.102.40.169:44047
```

## [ARCHIVE (8831/8831)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.133.100:51327
1.0.205.87:8080
1.1.189.58:8080
1.1.231.200:4145
1.2.202.165:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.168.12:4145
1.4.214.148:5678
1.9.71.4:4153
1.9.165.67:4153
1.10.140.43:4145
1.10.141.220:54620
1.10.187.237:5678
1.10.188.78:45208
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.96.156:4153
1.20.96.164:4153
1.20.99.41:5678
1.20.99.122:8080
1.20.137.82:32241
1.20.166.142:8080
1.20.184.75:4153
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.71.133.58:5678
1.116.4.222:7890
```



Thx Co Pure Gs - Sort Meister! 💟