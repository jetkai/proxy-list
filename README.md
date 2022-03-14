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

# [SAMPLE PROXIES] - [March 14 2022 | 01:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2325
   - **SOCKS5** -> 273
   - **HTTP** -> 738
   - **HTTPS** -> 616

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3952
   - **Unique Online Proxies** -> 3766
   - **Unique Online/Offline Proxies (Archive)** -> 57552

## [SOCKS4 (2325/3766)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.4.157.35:36202
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.20.96.30:4153
1.20.96.156:4153
1.20.96.164:4153
1.20.104.159:4145
1.20.227.66:4145
1.32.59.217:31981
1.55.241.4:4145
1.179.147.5:52210
1.179.148.9:36476
1.179.172.45:31225
1.179.186.68:1080
1.186.40.177:39651
1.186.82.4:5678
1.186.139.9:39651
1.186.213.67:5678
1.212.157.115:4145
2.183.8.145:4153
3.141.13.98:5678
3.144.165.41:5555
4.14.120.234:39593
4.28.96.138:39593
4.28.96.166:39593
5.22.154.50:32127
5.34.74.218:5678
```

## [SOCKS5 (273/3766)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.144.135.117:1080
5.188.211.50:7777
5.189.140.8:10439
8.214.69.237:10809
13.233.84.6:9999
31.128.248.1:1080
31.128.248.2:1080
31.130.89.218:1080
31.211.131.136:33427
34.95.224.52:443
36.26.4.118:7302
36.112.209.171:7302
37.139.243.32:1080
39.129.198.182:7302
39.152.105.58:7302
43.128.36.71:3389
43.129.222.186:38080
43.154.54.110:10808
43.224.10.32:6667
43.224.10.39:6667
43.224.10.57:6667
45.55.32.201:1540
45.67.229.101:30001
45.67.229.101:30003
45.67.229.104:30002
45.67.229.104:30003
45.67.229.104:30001
45.76.174.194:45559
45.88.14.197:8009
45.90.57.69:40021
```

## [HTTP (738/3766)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:80
1.10.141.220:54620
1.13.165.87:8080
1.13.165.87:33080
1.32.59.217:47045
1.186.40.35:1111
3.20.236.208:49205
3.85.7.155:8083
5.26.96.212:8080
5.104.174.199:23500
5.141.82.95:81
5.202.191.226:8080
8.214.41.50:80
14.177.236.212:55443
18.222.17.49:49205
24.43.140.138:8080
24.116.218.195:8080
27.72.149.205:8080
27.255.3.134:3128
31.3.169.45:8080
34.229.130.62:49205
34.230.89.25:49205
36.37.81.135:8080
36.66.124.193:3128
36.66.206.74:80
36.66.206.74:8080
36.80.51.175:8080
36.91.45.10:51672
36.91.107.61:8080
36.91.166.98:8080
```

## [HTTPS (616/3766)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.13.165.87:8080
1.15.182.239:7890
1.186.85.38:1111
5.16.0.174:8080
5.26.96.212:8080
5.34.153.142:8080
5.141.82.95:81
5.188.136.52:8080
5.189.186.24:5566
8.210.48.101:17200
8.214.41.50:80
13.59.34.132:443
14.139.184.130:3128
14.177.236.212:55443
14.241.225.167:8080
18.216.72.10:49205
18.222.17.49:49205
24.14.225.100:8118
27.42.168.46:55481
27.72.105.233:19132
27.109.116.28:55443
27.116.51.119:6666
27.116.51.181:6666
31.3.169.45:8080
31.3.169.53:8081
31.202.170.187:8080
31.204.180.44:53281
34.94.137.131:80
34.229.130.62:49205
36.66.19.10:8080
```

## [ARCHIVE (3766/57552)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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