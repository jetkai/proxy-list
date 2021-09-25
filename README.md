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

# [SAMPLE PROXIES] - [September 25 2021 | 11:29:34]

### Proxy Statistics:
- _Online Proxies (By Protocol):_## [SOCKS4 (4834/6048)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.4.157.35:36202
1.4.214.148:5678
1.9.165.67:4153
1.10.187.237:5678
1.20.95.95:5678
1.20.96.156:4153
1.20.96.164:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.220.79:4145
1.32.59.217:31981
1.55.241.4:4145
1.71.133.58:5678
1.179.147.5:52210
1.179.151.165:31948
1.179.173.114:4153
1.179.181.213:30500
1.179.186.68:1080
1.179.186.70:1080
1.179.186.71:1080
1.179.202.33:5678
1.186.40.177:39651
1.186.46.36:5678
1.186.82.4:5678
1.212.157.115:4145
1.220.145.45:4145
2.38.199.61:1080
2.135.223.134:5678
3.141.13.98:5678
```

## [SOCKS5 (248/6048)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks5.txt)
```yaml
5.56.134.237:45698
5.167.53.191:9999
8.129.71.143:1080
8.210.163.246:50008
8.210.163.246:8852
8.210.163.246:50031
8.210.163.246:50046
8.210.163.246:50026
8.210.163.246:50049
8.210.163.246:50007
8.210.163.246:50016
8.210.163.246:50009
8.210.163.246:50033
8.210.163.246:50027
8.210.163.246:50020
8.210.163.246:50017
8.210.163.246:50037
8.210.163.246:50030
8.210.163.246:50018
8.210.163.246:50023
8.210.163.246:50047
8.210.163.246:50014
8.210.163.246:50043
8.210.179.3:10086
8.210.251.244:6666
20.52.130.140:16379
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.119:6667
```

## [HTTP (703/6048)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-http.txt)
```yaml
1.1.189.58:8080
1.20.99.122:8080
1.20.217.221:8080
1.179.144.41:8080
1.179.183.73:50178
2.32.128.70:3128
3.20.236.208:49205
5.20.91.12:60792
5.130.90.3:8080
5.141.244.28:8080
5.183.71.145:39305
8.208.91.118:3128
8.208.91.118:8000
8.208.91.118:8888
14.161.252.185:55443
14.177.236.212:55443
14.241.111.38:8080
24.113.42.177:48678
24.172.34.114:49920
27.72.244.228:8080
27.105.130.93:8080
27.110.164.2:55443
27.116.51.119:8080
27.116.51.119:6666
27.116.51.181:6666
27.116.51.186:6666
31.172.177.149:83
31.173.94.93:43539
34.138.225.120:8888
36.37.86.60:60005
```

## [HTTPS (586/6048)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-https.txt)
```yaml
1.1.220.100:8080
1.32.59.217:47045
2.32.128.70:3128
5.20.91.12:60792
5.44.54.103:8080
8.129.10.162:3228
8.208.91.118:3128
8.243.120.54:999
14.160.26.153:8080
14.177.236.212:55443
14.241.111.38:8080
27.105.130.93:8080
27.109.116.28:55443
27.116.51.119:8080
27.116.51.119:6666
27.116.51.186:6666
27.191.60.216:3256
31.40.144.127:3128
31.172.177.149:83
34.138.225.120:8888
36.37.86.60:60005
36.37.160.242:8080
36.66.126.219:51009
36.66.172.121:39810
36.67.11.41:8080
36.67.57.45:30066
36.67.66.100:30142
36.67.251.161:38288
36.89.89.167:8888
36.89.169.235:8080
```

## [ARCHIVE (6048/52909)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
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
1.0.212.209:4145
1.0.213.150:5678
1.0.215.76:5678
1.0.215.239:5678
1.0.225.117:5678
1.0.251.164:4145
1.1.160.205:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
1.1.227.203:4145
1.1.229.183:5678
1.1.245.173:5678
1.2.167.37:4145
1.2.171.107:5678
1.2.187.79:4145
1.2.187.87:5678
```



Thx Co Pure Gs - Sort Meister! 💟