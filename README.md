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

# [SAMPLE PROXIES] - [September 25 2021 | 05:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - SOCKS4: 3559
   - SOCKS5: 286
   - HTTP: 0
   - HTTPS: 0
Total Online Proxies (SOCKS4/5 + HTTP/S): 3845
Unique Online Proxies: 3690
Unique Online/Offline Proxies (Archive): 53959
## [SOCKS4 (3559/3690)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.1.230.183:5678
1.1.231.200:4145
1.4.168.12:4145
1.6.216.46:9999
1.9.71.4:4153
1.9.164.242:35471
1.9.167.36:60489
1.10.140.43:4145
1.20.96.156:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.168.157:4145
1.20.184.75:4153
1.53.137.84:4145
1.55.241.4:4145
1.71.133.58:5678
1.179.147.5:52210
1.179.181.213:30500
1.179.186.69:1080
1.179.186.71:1080
1.179.201.189:5678
1.179.202.33:5678
1.180.133.138:1080
1.186.40.2:39651
1.186.40.157:39651
1.186.82.4:5678
1.186.139.9:39651
1.234.35.150:1080
1.234.35.172:1080
```

## [SOCKS5 (286/3690)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks5.txt)
```yaml
1.116.4.222:7890
5.61.53.57:9100
5.61.53.57:9341
5.61.53.57:9052
5.61.53.57:9053
5.61.53.57:9300
5.61.53.57:9090
8.131.254.15:9999
8.210.163.246:50010
8.210.163.246:50049
8.210.163.246:50004
8.210.163.246:50026
8.210.163.246:50014
8.210.163.246:50031
8.210.163.246:50023
8.210.163.246:50009
8.210.163.246:50022
8.210.163.246:50024
8.210.163.246:50041
8.210.163.246:50015
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.186:6667
36.27.223.70:31493
36.94.126.50:1080
37.156.104.178:3327
39.96.175.55:1080
39.106.49.107:1080
39.107.88.218:1080
```

## [HTTP (0/3690)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-http.txt)
```yaml

```

## [HTTPS (0/3690)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-https.txt)
```yaml

```

## [ARCHIVE (3690/53959)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
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
1.1.230.183:5678
1.1.231.200:4145
1.1.245.173:5678
1.2.167.37:4145
1.2.171.107:5678
```



Thx Co Pure Gs - Sort Meister! 💟