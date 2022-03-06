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

# [SAMPLE PROXIES] - [March 06 2022 | 09:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1511
   - **SOCKS5** -> 533
   - **HTTP** -> 882
   - **HTTPS** -> 841

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3767
   - **Unique Online Proxies** -> 3425
   - **Unique Online/Offline Proxies (Archive)** -> 56699

## [SOCKS4 (1511/3425)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.10.141.220:37718
1.10.189.133:50855
1.32.57.85:5678
1.53.137.84:4145
1.179.148.9:36476
1.179.202.33:5678
1.186.40.9:39651
1.186.82.4:5678
1.212.157.115:4145
1.234.56.20:18638
2.179.167.29:9969
3.141.13.98:5678
3.144.165.41:5555
5.9.13.8:9050
5.34.74.218:5678
5.34.74.234:5678
5.56.133.204:4444
5.152.86.46:14888
5.160.72.149:43130
5.160.184.243:4145
5.172.188.90:5678
5.180.100.24:5678
5.188.64.79:5678
5.190.60.221:3629
8.39.228.5:39593
8.39.228.209:39593
8.40.133.10:1099
```

## [SOCKS5 (533/3425)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.15.182.239:7890
1.234.56.20:18638
5.9.13.8:9050
5.130.125.67:1080
5.144.135.117:1080
8.214.69.237:10809
13.233.84.6:9999
23.94.73.246:1080
24.95.52.104:3820
24.249.199.4:4145
24.249.199.12:4145
31.128.248.2:1080
31.130.89.218:1080
31.186.241.7:31075
34.95.224.52:443
34.134.60.185:443
36.26.4.118:7302
36.133.38.6:84
36.133.38.6:83
36.133.183.241:88
36.133.183.241:82
36.133.183.241:92
36.133.183.241:84
36.133.202.102:86
36.133.202.102:85
36.133.202.102:82
36.133.202.102:88
36.133.214.97:84
36.133.214.97:93
36.133.214.97:85
```

## [HTTP (882/3425)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:80
1.2.252.65:8080
1.179.136.98:8080
1.180.156.226:65001
1.186.40.35:1111
3.20.236.208:49205
5.34.153.142:8080
5.56.133.132:3128
5.58.33.187:55507
5.101.98.235:3128
5.149.219.201:8080
5.160.101.170:3128
5.188.136.52:8080
8.208.91.118:8081
8.208.91.118:8888
8.208.91.118:3128
8.214.41.50:80
8.242.207.202:8080
14.143.168.230:8080
14.160.26.153:8080
14.161.252.185:55443
14.192.3.161:83
14.207.144.47:9080
14.241.242.9:9090
18.216.72.10:49205
18.222.17.49:49205
23.140.80.50:8080
24.227.247.186:8080
27.116.51.186:6666
27.147.209.215:8080
```

## [HTTPS (841/3425)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.220.100:8080
1.2.252.65:8080
1.13.165.87:8080
1.15.182.239:7890
1.20.217.52:8080
1.180.156.226:65001
1.186.40.35:1111
2.188.166.22:3128
3.20.236.208:49205
5.20.91.12:60792
5.101.98.235:3128
5.134.221.222:8080
5.139.161.156:55443
5.141.82.95:81
5.202.191.226:8080
8.208.91.118:80
8.214.41.50:80
8.242.142.182:999
12.218.209.130:53281
14.54.27.37:4004
14.143.168.230:8080
14.160.26.153:8080
14.207.149.70:8080
14.215.212.37:9168
18.216.72.10:49205
18.222.17.49:49205
20.74.169.104:8118
23.95.186.190:65000
27.72.105.233:19132
27.72.149.205:8080
```

## [ARCHIVE (3425/56699)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.42:4145
1.0.136.161:4145
1.0.136.168:4145
1.0.136.201:4145
1.0.136.222:4145
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.157.49:4145
1.0.160.106:4153
1.0.161.151:4153
1.0.162.24:4145
1.0.162.181:4145
1.0.163.17:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.170.50:80
1.0.173.104:4145
1.0.174.87:4145
1.0.190.19:4145
1.0.191.138:4153
1.0.205.87:8080
1.0.209.116:4145
```



Thx Co Pure Gs - Sort Meister! 💟