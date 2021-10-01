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
   - **SOCKS4** -> 4270
   - **SOCKS5** -> 166
   - **HTTP** -> 1123
   - **HTTPS** -> 1057

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 6616
   - **Unique Online Proxies** -> 6171
   - **Unique Online/Offline Proxies (Archive)** -> 55307

## [SOCKS4 (4270/6171)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.4.214.148:5678
1.6.216.46:9999
1.9.165.67:4153
1.9.167.36:60489
1.10.140.43:4145
1.10.187.237:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.168.157:4145
1.20.220.79:4145
1.32.57.85:5678
1.32.59.217:31981
1.179.130.201:4153
1.179.145.101:33109
1.179.147.5:52210
1.179.151.165:31948
1.179.172.45:31225
1.179.173.114:4153
1.179.181.213:30500
1.179.183.73:61468
1.179.201.189:5678
1.179.202.33:5678
1.186.40.2:39651
1.186.40.9:39651
1.186.46.36:5678
1.212.157.115:4145
```

## [SOCKS5 (166/6171)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.164.23.101:1080
8.129.25.203:9999
8.131.254.15:9999
24.249.199.4:4145
24.249.199.14:57335
31.7.232.178:1080
31.128.248.2:1080
36.94.126.50:1080
39.103.216.155:7890
43.128.13.103:28010
43.224.8.12:6667
43.224.8.14:6667
43.224.8.116:6667
43.224.10.26:6667
43.224.10.27:6667
43.224.10.33:6667
43.224.10.35:6667
43.224.10.37:6667
43.224.10.48:6667
45.149.76.42:9051
45.221.76.114:8080
47.52.238.234:10086
47.75.113.110:10015
47.105.138.127:8888
47.115.149.82:443
47.149.68.132:1080
52.175.21.231:1080
59.66.132.22:7890
67.201.33.10:25283
70.166.167.36:4145
```

## [HTTP (1123/6171)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.10.141.220:54620
1.179.148.9:55636
1.179.217.210:8080
3.20.236.208:49205
5.16.0.186:8080
5.20.91.12:60792
5.183.71.145:39305
5.188.154.149:8080
8.129.10.162:3228
8.208.91.118:8080
8.208.91.118:8081
8.208.91.118:8800
8.214.2.182:7890
12.139.210.121:8080
13.229.47.250:8118
14.102.152.158:8080
14.241.111.38:8080
14.241.225.134:443
14.241.225.167:8080
18.197.97.162:9300
18.220.20.81:8080
24.113.42.177:48678
27.72.244.228:8080
27.109.116.28:55443
27.109.116.119:23500
27.111.45.18:55443
27.121.85.74:8080
27.131.179.216:10443
27.191.60.79:3256
27.191.60.144:3256
```

## [HTTPS (1057/6171)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.32.59.217:47045
1.179.183.73:50178
1.179.217.210:8080
2.32.128.70:3128
2.180.33.122:8083
5.16.0.180:8080
5.20.91.12:60792
5.56.133.225:7890
5.59.136.230:8080
5.149.219.201:8080
5.160.91.130:3128
5.164.211.117:8080
8.208.91.118:80
8.208.91.118:8000
8.208.91.118:3128
8.214.2.182:7890
8.242.215.250:999
12.127.133.62:48678
14.102.44.1:44047
14.102.44.25:44047
14.160.26.153:8080
14.192.2.161:83
14.192.148.170:3128
18.220.20.81:8080
24.113.42.177:48678
27.22.85.58:8100
27.110.167.164:8080
27.116.63.120:7999
27.121.85.74:8080
27.123.1.46:3128
```

## [ARCHIVE (6171/55307)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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