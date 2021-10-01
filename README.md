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

# [SAMPLE PROXIES] - [October 01 2021 | 04:05:05]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 186
   - **SOCKS5** -> 5
   - **HTTP** -> 53
   - **HTTPS** -> 445

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 689
   - **Unique Online Proxies** -> 674
   - **Unique Online/Offline Proxies (Archive)** -> 55952

## [SOCKS4 (186/674)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.1.154.73:4145
5.202.159.24:5678
5.206.238.32:5678
24.76.16.12:5678
31.129.249.38:5678
31.207.188.96:5678
31.207.210.199:3629
36.37.71.83:5430
36.89.165.21:5678
36.90.77.12:5678
37.32.40.107:5678
37.189.227.97:4153
41.57.156.202:5678
41.71.1.184:5678
41.75.133.241:5678
41.215.28.110:5678
43.224.10.8:6667
43.254.224.147:1080
45.7.225.100:4153
45.71.148.141:4651
45.144.205.227:8376
45.157.52.196:5678
45.165.144.198:5678
45.167.56.94:5678
45.168.12.41:3629
45.168.25.166:5678
45.172.225.26:4153
45.179.190.242:5678
45.180.41.152:4153
45.185.172.154:5678
```

## [SOCKS5 (5/674)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
27.156.185.35:44406
43.254.224.147:1080
119.28.68.69:1080
161.35.149.100:1080
192.99.152.135:1080
```

## [HTTP (53/674)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
5.160.151.109:8080
31.204.172.176:8080
36.66.103.211:3128
36.92.246.227:8080
36.95.80.147:8080
43.229.254.116:8080
45.65.168.250:8080
45.160.15.129:999
45.167.194.11:999
45.183.142.117:999
51.75.49.208:37951
58.147.186.10:8080
66.70.198.229:999
82.137.244.74:8080
95.0.66.40:9090
103.50.254.171:3128
103.78.97.18:8080
103.94.122.14:8080
103.103.3.6:8080
103.120.163.117:6969
103.145.210.246:8080
103.147.32.146:8080
103.148.2.82:8181
103.161.3.19:8080
103.167.35.116:8080
103.234.254.154:8080
109.173.41.190:8080
110.78.147.149:80
112.78.164.153:8080
118.99.96.59:8080
```

## [HTTPS (445/674)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.15.139.38:7890
1.15.228.75:8118
1.32.44.17:8080
1.71.132.216:6969
1.116.155.200:7788
2.188.166.26:3128
3.82.92.51:49205
3.82.186.15:49205
3.83.243.92:49205
3.84.17.68:49205
3.86.23.10:49205
3.86.147.133:49205
3.95.161.236:49205
3.135.233.222:49205
3.142.122.90:49205
8.129.129.23:9999
12.139.210.169:8080
14.169.244.18:9999
14.207.201.37:8080
18.118.18.237:49205
18.208.155.244:49205
18.212.179.196:8080
18.216.52.118:49205
18.216.214.236:49205
18.220.58.16:49205
27.46.55.28:9797
27.72.90.102:8080
27.191.60.117:3256
27.191.60.166:3256
27.191.60.169:3256
```

## [ARCHIVE (674/55952)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.1.154.73:4145
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
```



Thx Co Pure Gs - Sort Meister! 💟