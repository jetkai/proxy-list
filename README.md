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

# [SAMPLE PROXIES] - [September 26 2021 | 09:29:08]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - SOCKS4: 4867
   - SOCKS5: 489
   - HTTP: 1420
   - HTTPS: 1244

- _Extra Stats_
   - Total Online Proxies (SOCKS4/5 + HTTP/S): 8020

   - Unique Online Proxies: 7153

   - Unique Online/Offline Proxies (Archive): 55083

## [SOCKS4 (4867/7153)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.0.209.45:4145
1.1.231.200:4145
1.2.202.165:4145
1.4.157.35:36202
1.9.71.4:4153
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.187.237:5678
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.96.156:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.168.157:4145
1.20.227.66:4145
1.32.59.217:31981
1.53.137.84:4145
1.53.137.164:4145
1.55.241.4:4145
1.71.133.58:5678
1.179.145.101:33109
1.179.147.5:52210
1.179.172.45:31225
1.179.173.114:4153
1.179.181.213:30500
```

## [SOCKS5 (489/7153)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-socks5.txt)
```yaml
1.116.4.222:7890
1.180.133.138:1080
5.34.180.128:9050
5.56.134.237:45698
5.61.53.57:9211
5.61.53.57:9052
5.61.53.57:9090
5.61.53.57:9341
5.61.53.57:9300
5.61.53.57:9503
5.61.53.57:9100
5.164.23.101:1080
5.167.53.191:9999
8.210.163.246:50011
8.210.163.246:50009
8.210.163.246:50037
8.210.163.246:50022
8.210.163.246:50047
8.210.163.246:50049
8.210.163.246:50042
8.210.163.246:50023
8.210.163.246:50008
8.210.163.246:50027
8.210.163.246:50040
8.210.163.246:50025
8.210.163.246:50015
8.210.163.246:50035
8.210.251.244:6666
8.210.251.244:24691
20.52.130.140:16379
```

## [HTTP (1420/7153)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-http.txt)
```yaml
1.0.205.87:8080
1.1.189.58:8080
1.4.157.35:46944
1.10.141.220:54620
1.10.187.237:8080
1.10.188.78:45208
1.116.4.222:7890
1.179.144.41:8080
2.32.128.70:3128
3.20.236.208:49205
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.44.54.103:8080
5.44.54.106:8080
5.56.134.237:55963
5.130.90.3:8080
5.141.244.28:8080
5.149.219.201:8080
5.188.154.149:8080
5.190.29.161:8080
5.196.196.195:8118
8.129.10.162:3228
8.208.91.118:8008
8.208.91.118:8080
8.208.91.118:8888
8.208.91.118:8000
8.208.91.118:81
8.208.91.118:8081
8.214.2.182:7890
```

## [HTTPS (1244/7153)](https://raw.githubusercontent.com/jetkai/proxy-list/main/proxies-https.txt)
```yaml
1.4.157.35:46944
1.20.99.122:8080
1.20.207.200:8080
1.32.59.217:47045
1.179.144.41:8080
2.32.128.70:3128
5.16.0.49:8080
5.16.0.174:8080
5.20.91.12:60792
5.44.54.16:8080
5.44.54.103:8080
5.56.134.237:55963
5.130.90.3:8080
5.141.244.28:8080
5.149.219.201:8080
5.183.71.145:39305
5.183.234.1:8080
5.190.29.161:8080
8.129.10.162:3228
8.243.120.54:999
8.243.138.218:999
12.127.133.62:48678
14.102.13.161:8080
14.102.152.158:8080
14.160.32.23:8080
14.207.3.29:8080
14.207.57.244:8080
14.241.111.38:8080
14.241.225.134:443
14.241.225.167:80
```

## [ARCHIVE (7153/55083)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/working-proxies-history.txt)
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