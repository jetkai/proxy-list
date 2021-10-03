<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jetkai/proxy-list?style=flat&logo=github
[contributors-url]: https://github.com/jetkai/proxy-list/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jetkai/proxy-list?style=flat&logo=github
[forks-url]: https://github.com/jetkai/proxy-list/network/members
[stars-shield]: https://img.shields.io/github/stars/jetkai/proxy-list?style=flat&logo=github
[stars-url]: https://github.com/jetkai/proxy-list/stargazers
[issues-shield]: https://img.shields.io/github/issues/jetkai/proxy-list?style=flat&logo=github
[issues-url]: https://github.com/jetkai/proxy-list/issues
[license-shield]: https://img.shields.io/github/license/jetkai/proxy-list?style=flat&logo=github
[license-url]: https://github.com/jetkai/proxy-list/blob/main/LICENSE
[commit-shield]: https://img.shields.io/github/last-commit/jetkai/proxy-list?style=flat&logo=github
[commit-url]: https://github.com/jetkai/proxy-list/commits/main
[commit-activity]: https://img.shields.io/github/commit-activity/w/jetkai/proxy-list?style=flat&logo=github
[commit-activity-url]: https://github.com/jetkai/proxy-list/commits/main

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE & READY

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

## 📰About This Project & The Proxies:
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT** & **CSV** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing:

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom|EU
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/ProxyBuilder/blob/main/src/main/kotlin/spb/net/proxy/ProxyTester.kt)
```kotlin
    //SOCKS example (HTTP/S) is also supported
    private fun useSocksProxy(serverAddress: String?, serverPort: Int): ClientSocket? {
        val proxy = Proxy(Proxy.Type.SOCKS, InetSocketAddress(proxyAddress, proxyPort))
        val socket = Socket(proxy)
        if(socks4)
            forceSocks4(socket)
        try {
            socket.soTimeout = Constants.CONNECTION_TIMEOUT //3000ms
            socket.tcpNoDelay = true
            socket.connect(InetSocketAddress(serverAddress, serverPort), Constants.CONNECTION_TIMEOUT)
        } catch (e : IOException) {
            socket.close()
        }
        if(socket.isClosed)
            return null
        return ClientSocket().init(socket) //Read/Write Data Function
    }
```

## 📝Proxy Formatting:

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability:

Proxies work for any application that can establish a socket connection, such as... An application that has proxy support (FireFox, Chrome), or as an example, these Java Apps -> [JaySyiPker](https://github.com/JayArrowz/JaySyiPker), [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS) & [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final).

## 🔗ProxyList Links (Direct URL):

- _Online Proxies:_
    - **JSON** -> [proxies.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json)
    - **TXT** -> [proxies.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt)
    - **CSV** -> [proxies.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6719)
Most Detected Proxies By Country|Brazil (4652)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2449)
Most Proxies By Port|5678 (33610)
Most Proxies By Protocol|SOCKS4 (43928)
Most Proxies By Continent|Asia (27600)

**Name**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xlsx/analysis.xlsx)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)

![image](https://user-images.githubusercontent.com/26250917/135737945-c275ad3d-e086-4d3c-b593-a9096362e673.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [October 03 2021 | 03:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 6908
   - **SOCKS5** -> 247
   - **HTTP** -> 1007
   - **HTTPS** -> 1006

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 9168
   - **Unique Online Proxies** -> 8772
   - **Unique Online/Offline Proxies (Archive)** -> 57549

## [SOCKS4 (6908/8772)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.136.183:4145
1.0.152.157:4145
1.1.161.198:4145
1.4.214.148:5678
1.6.216.46:9999
1.9.71.4:4153
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:37718
1.20.95.95:5678
1.20.96.30:4153
1.20.99.41:5678
1.20.168.157:4145
1.20.184.75:4153
1.20.203.220:4145
1.20.207.200:4145
1.20.220.79:4145
1.32.57.85:5678
1.53.137.84:4145
1.53.137.164:4145
1.71.133.58:5678
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.172.45:31225
```

## [SOCKS5 (247/8772)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.105.0.135:16379
5.105.1.86:16379
5.164.23.101:1080
8.210.251.244:6666
13.250.172.147:48540
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.22.85.52:8100
27.116.51.85:6667
27.116.51.92:6667
27.116.51.119:6667
27.116.51.186:6667
31.7.232.178:1080
31.128.248.1:1080
31.128.248.2:1080
36.27.223.70:25739
36.89.86.49:56845
39.105.134.60:10705
41.231.54.69:3000
43.132.157.62:2120
43.224.10.8:6667
43.224.10.13:6667
43.224.10.23:6667
43.224.10.26:6667
43.224.10.27:6667
43.224.10.31:6667
43.224.10.32:6667
43.224.10.37:6667
43.224.10.43:6667
```

## [HTTP (1007/8772)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.4.157.35:46944
1.10.188.78:45208
1.15.182.239:7890
1.20.217.221:8080
1.116.4.222:7890
2.59.76.233:53281
2.188.166.22:3128
2.188.166.26:3128
3.82.233.197:49205
5.16.0.49:8080
5.16.0.97:1256
5.16.0.180:8080
5.16.0.186:8080
5.34.153.142:8080
5.44.54.103:8080
5.183.234.1:8080
5.227.65.88:3128
8.208.91.118:8081
8.208.91.118:8000
8.208.91.118:8008
8.208.91.118:8080
8.208.91.118:80
8.214.2.182:7890
8.242.215.250:999
8.243.120.54:999
14.102.152.157:8080
14.102.152.158:8080
14.177.236.212:55443
14.192.148.170:3128
14.241.111.38:8080
```

## [HTTPS (1006/8772)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.20.166.142:8080
1.32.44.17:8080
1.116.155.200:7788
1.179.144.41:8080
2.188.166.25:3128
3.83.243.92:49205
3.84.17.68:49205
3.86.23.10:49205
3.95.161.236:49205
3.142.122.90:49205
5.42.110.2:6969
5.56.133.225:7890
5.58.33.187:55507
5.167.121.106:8080
8.208.91.118:8800
8.208.91.118:8008
8.208.91.118:80
12.127.133.62:48678
14.169.244.18:9999
14.192.148.170:3128
14.241.225.167:443
18.208.155.244:49205
18.216.28.191:49205
18.220.20.81:8080
24.113.42.177:48678
27.46.55.28:9797
27.116.51.85:6666
27.116.63.120:7999
27.191.60.14:3256
27.191.60.45:3256
```

## [ARCHIVE (8772/57549)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.136.183:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.152.157:4145
1.0.160.160:4145
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
1.1.161.198:4145
1.1.185.208:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
1.1.225.97:5678
1.1.226.87:5678
1.1.226.224:5678
1.1.227.33:5678
```



Thx Co Pure Gs - Sort Meister! 💟