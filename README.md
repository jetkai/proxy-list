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

# [SAMPLE PROXIES] - [January 09 2022 | 01:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 5006
   - **SOCKS5** -> 456
   - **HTTP** -> 2211
   - **HTTPS** -> 2241

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 9914
   - **Unique Online Proxies** -> 8576
   - **Unique Online/Offline Proxies (Archive)** -> 43507

## [SOCKS4 (5006/8576)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.0.162.181:4145
1.0.242.224:4145
1.1.128.58:5678
1.1.225.141:4145
1.4.157.35:36202
1.4.195.114:4145
1.4.214.148:5678
1.4.250.132:5678
1.9.27.217:4153
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.141.220:37718
1.14.108.182:1080
1.20.95.95:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.198.9:4153
1.20.198.10:4153
1.20.220.79:4145
1.20.227.66:4145
1.20.235.153:5678
1.32.57.85:5678
1.32.59.217:31981
1.53.137.164:4145
1.55.241.4:4145
1.83.154.35:4145
1.179.173.114:4153
```

## [SOCKS5 (456/8576)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
4.79.207.214:9050
5.56.134.237:45698
5.160.38.245:1080
8.214.82.70:1080
8.218.219.172:15132
18.181.146.180:1088
18.223.3.192:11086
20.205.204.111:6666
23.94.149.131:53335
24.249.199.4:4145
24.249.199.12:4145
27.116.51.85:6667
27.116.51.178:6667
27.156.80.128:16790
27.156.80.173:16790
27.156.80.237:16790
31.128.248.1:1080
31.186.241.7:33532
31.211.131.136:33427
34.80.219.241:1000
36.89.86.49:56845
36.94.126.50:1080
37.152.180.224:2327
37.152.180.224:49227
37.156.104.178:3327
39.104.129.141:7302
39.108.226.136:9080
39.165.98.152:7302
41.216.163.66:5678
42.248.122.83:9999
```

## [HTTP (2211/8576)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.4.201.129:8080
1.4.250.132:8080
1.9.213.163:8080
1.13.165.87:8080
1.15.182.239:7890
1.20.163.161:8080
1.20.217.149:8080
1.32.59.217:47045
1.53.21.28:4003
1.117.231.98:8080
1.179.148.9:55636
1.179.239.49:8080
1.182.90.40:7890
2.188.166.25:3128
3.20.236.208:49205
3.215.177.148:49205
5.15.184.45:8080
5.16.0.49:8080
5.16.0.97:1256
5.16.0.174:8080
5.16.0.180:8080
5.16.7.213:1256
5.20.91.12:60792
5.34.153.142:8080
5.58.33.187:55507
5.130.90.3:8080
5.135.182.184:4433
5.141.82.95:81
5.141.244.97:61288
5.160.91.130:3128
```

## [HTTPS (2241/8576)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:80
1.2.252.65:8080
1.4.201.129:8080
1.9.213.163:8080
1.10.141.220:54620
1.13.165.87:8080
1.15.182.239:7890
1.20.163.161:8080
1.20.217.149:8080
1.53.21.28:4005
1.179.136.98:8080
1.179.239.49:8080
2.137.213.1:8080
2.184.4.76:6565
3.20.236.208:49205
3.145.135.10:3128
5.9.89.187:808
5.15.184.45:8080
5.16.0.49:8080
5.16.0.77:1256
5.16.0.174:8080
5.16.0.180:8080
5.16.7.213:1256
5.20.91.12:60792
5.26.96.212:8080
5.34.153.142:8080
5.35.90.173:8888
5.59.136.230:8080
5.131.243.11:8080
5.131.243.252:8080
```

## [ARCHIVE (8576/43507)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.42:4145
1.0.136.168:4145
1.0.136.201:4145
1.0.136.222:4145
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
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
1.0.205.87:8080
1.0.209.187:8080
1.0.213.133:8080
1.0.220.169:4153
1.0.226.138:4145
1.0.228.243:5678
1.0.229.154:5678
```



Thx Co Pure Gs - Sort Meister! 💟