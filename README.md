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
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

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
    - **XML** -> [proxies.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml)
    - **YAML** -> [proxies.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)
- _Online/Offline Proxies (Archive):_
  - **JSON** -> [working-proxies-history.json](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history.json)
  - **TXT** -> [working-proxies-history.txt](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
  - **CSV** -> [working-proxies-history.csv](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history.csv)
  - **XML** -> [working-proxies-history.xml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history.xml)
  - **YAML** -> [working-proxies-history.yaml](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history.yaml)

## 🌍Geolocation & Graphs (Weekly):
Analytics are updated on a weekly basis and contains raw data, tables & graphs. 

You can view/download this data below.

**Query**|**Result**
:-----:|:-----:
Most Proxies By Country|Brazil (6749)
Most Detected Proxies By Country|Brazil (4680)
Most Proxies By Provider|Bharat Sanchar Nigam Ltd (2455)
Most Proxies By Port|5678 (33668)
Most Proxies By Protocol|SOCKS4 (44037)
Most Proxies By Continent|Asia (27864)

**Data Type**|**Link**
:-----:|:-----:
Graphs, Tables & Data (Excel) | [(analysis.xlsx)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xlsx/analysis.xlsx)
Raw Data (JSON) | [(archive-geo.json)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/working-proxies-history-geo-beautify.json)
Raw Data (CSV) | [(archive-geo.csv)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/working-proxies-history-geo.csv)
Raw Data (XML) | [(archive-geo.xml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/working-proxies-history-geo.xml)
Raw Data (YAML) | [(archive-geo.yaml)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/working-proxies-history-geo.yaml)

![image](https://user-images.githubusercontent.com/26250917/135766207-17d4c531-2738-4209-808e-82c04b871331.png)


## Next Updates:

Further updates will be made to this project throughout the year, the next update I am working on will keep a record of proxy up-time, location, isp & speed.

---

# [SAMPLE PROXIES] - [October 13 2021 | 03:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 7258
   - **SOCKS5** -> 345
   - **HTTP** -> 2603
   - **HTTPS** -> 2253

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 12459
   - **Unique Online Proxies** -> 11160
   - **Unique Online/Offline Proxies (Archive)** -> 64091

## [SOCKS4 (7258/11160)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.148.132:4145
1.0.152.157:4145
1.0.239.61:5678
1.1.129.166:4145
1.1.187.210:4145
1.1.229.44:4145
1.4.154.110:5678
1.4.157.35:36202
1.4.214.148:5678
1.9.27.213:4153
1.9.71.4:4153
1.9.164.242:35471
1.9.165.67:4153
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.187.237:5678
1.20.95.95:5678
1.20.96.164:4153
1.20.99.41:5678
1.20.137.82:32241
1.20.168.157:4145
1.20.203.14:4145
1.20.220.79:4145
1.20.227.66:4145
1.32.57.85:5678
1.32.59.217:31981
1.53.137.84:4145
1.55.241.4:4145
1.71.133.58:5678
```

## [SOCKS5 (345/11160)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.70.174.113:1088
5.34.247.119:12356
5.34.247.146:12356
5.34.247.215:12356
5.45.73.63:9050
5.56.134.237:45698
5.61.53.57:9054
5.61.53.57:9177
5.61.53.57:9091
5.105.0.135:16379
5.105.1.86:16379
5.164.23.101:1080
5.167.53.191:9999
8.131.71.241:1080
8.210.163.246:50016
8.210.163.246:50032
8.210.163.246:50039
13.250.172.147:48540
20.52.130.140:16379
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.116.51.85:6667
27.116.51.178:6667
27.116.51.186:6667
31.7.232.178:1080
31.128.248.1:1080
31.128.248.2:1080
31.186.241.7:52185
36.27.223.80:44322
```

## [HTTP (2603/11160)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.220.100:8080
1.2.252.65:8080
1.10.141.220:54620
1.10.187.237:8080
1.10.188.78:45208
1.15.182.239:7890
1.20.99.122:8080
1.20.166.142:8080
1.20.217.221:8080
1.116.4.222:7890
1.116.12.21:3228
1.116.78.80:7890
1.179.148.9:55636
1.179.183.73:50178
1.179.217.210:8080
2.56.240.137:8080
2.188.166.25:3128
3.14.1.220:49205
3.14.28.166:49205
3.15.8.4:49205
3.15.232.102:49205
3.16.128.220:49205
3.17.148.147:49205
3.20.236.208:49205
3.22.175.45:49205
3.84.127.192:49205
3.87.223.98:49205
3.87.228.41:49205
3.90.235.224:49205
3.135.231.173:49205
```

## [HTTPS (2253/11160)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.4.198.94:8081
1.10.141.220:54620
1.15.182.239:7890
1.20.99.122:8080
1.20.166.142:8080
1.20.217.52:8080
1.116.4.222:7890
1.116.12.21:3228
1.179.136.98:8080
1.179.144.41:8080
1.179.217.210:8080
2.184.4.68:6565
3.14.28.166:49205
3.15.196.67:49205
3.15.232.102:49205
3.17.148.147:49205
3.22.175.45:49205
3.83.8.112:49205
3.87.194.216:49205
3.87.228.41:49205
3.88.202.89:49205
3.94.93.17:49205
3.135.231.69:49205
3.135.231.173:49205
3.135.233.222:49205
3.138.196.88:49205
3.142.120.122:49205
3.142.122.90:49205
3.142.237.56:49205
3.143.211.41:49205
```

## [ARCHIVE (11160/64091)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.51:4145
1.0.136.115:4145
1.0.136.183:4145
1.0.137.117:5678
1.0.144.14:5678
1.0.148.132:4145
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
1.0.239.61:5678
1.0.251.164:4145
1.1.129.166:4145
1.1.154.73:4145
1.1.160.205:4145
1.1.161.198:4145
1.1.185.208:4145
1.1.187.210:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.224.68:5678
```



Thx Co Pure Gs - Sort Meister! 💟