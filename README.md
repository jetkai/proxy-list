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

# [SAMPLE PROXIES] - [September 26 2021 | 03:31:36]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - SOCKS4: 5890
   - SOCKS5: 412
   - HTTP: 925
   - HTTPS: 1009

Total Online Proxies (SOCKS4/5 + HTTP/S): 8236

Unique Online Proxies: 7704

Unique Online/Offline Proxies (Archive): 54333

## [SOCKS4 (5890/7704)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.1.185.208:4145
1.1.230.183:5678
1.1.231.200:4145
1.2.199.191:3629
1.2.202.165:4145
1.4.168.12:4145
1.4.214.148:5678
1.9.164.242:35471
1.9.165.67:4153
1.9.167.35:60489
1.9.167.36:60489
1.20.95.95:5678
1.20.96.30:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.168.157:4145
1.20.184.75:4153
1.20.207.28:4153
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.53.137.84:4145
1.53.137.164:4145
1.55.241.4:4145
1.71.133.58:5678
1.179.147.5:52210
1.179.173.114:4153
1.179.181.213:30500
1.179.186.68:1080
```

## [SOCKS5 (412/7704)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks5.txt)
```yaml
1.116.4.222:7890
5.45.73.63:9050
5.56.134.237:45698
5.164.23.101:1080
8.210.163.246:50004
8.210.163.246:50028
8.210.163.246:50032
8.210.163.246:50049
8.210.163.246:50041
8.210.163.246:50039
8.210.163.246:50023
8.210.163.246:50001
8.210.163.246:50025
8.210.163.246:50026
8.210.163.246:50038
8.210.163.246:50046
8.210.179.3:10086
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.119:6667
27.116.51.178:6667
27.116.51.181:6667
27.116.51.186:6667
27.151.13.149:38801
31.128.248.1:1080
31.186.241.7:52185
35.223.101.235:9050
36.27.223.70:31493
37.156.104.178:3327
```

## [HTTP (925/7704)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-http.txt)
```yaml
1.10.187.237:8080
1.20.166.142:8080
1.179.183.73:50178
1.179.217.210:8080
2.32.128.70:3128
2.59.76.233:53281
5.20.91.12:60792
5.34.153.142:8080
5.58.33.187:55507
5.59.136.230:8080
5.130.90.3:8080
5.149.219.201:8080
05.149.219.201:8080
14.160.32.23:8080
14.161.10.191:8080
14.177.235.17:8080
18.220.20.81:8080
23.101.58.2:3128
24.106.221.230:53281
24.172.82.94:53281
27.72.244.228:8080
27.109.116.28:55443
27.116.51.85:6666
27.116.51.119:6666
27.116.51.186:6666
27.116.63.120:7999
27.131.179.197:10443
27.147.219.46:8080
27.191.60.87:3256
31.40.144.127:3128
```

## [HTTPS (1009/7704)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-https.txt)
```yaml
1.20.166.142:8080
1.20.217.221:8080
1.179.144.41:8080
2.32.128.70:3128
5.16.0.77:1256
5.16.0.174:8080
5.20.91.12:60792
5.56.134.237:55963
5.133.27.61:3129
5.149.219.201:8080
5.183.71.145:39305
5.183.234.1:8080
5.188.154.149:8080
8.129.10.162:3228
8.208.91.118:81
8.243.120.54:999
12.139.210.121:8080
12.229.217.226:55443
13.114.169.206:8000
14.160.32.23:8080
14.161.252.185:55443
14.192.2.161:83
14.207.3.29:8080
14.241.225.167:8080
18.220.20.81:8080
24.113.42.177:48678
27.72.95.176:8080
27.72.149.205:8080
27.110.164.2:55443
27.116.51.181:6666
```

## [ARCHIVE (7704/54333)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
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
1.2.167.37:4145
```



Thx Co Pure Gs - Sort Meister! 💟