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

# [SAMPLE PROXIES] - [November 14 2021 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3841
   - **SOCKS5** -> 322
   - **HTTP** -> 1785
   - **HTTPS** -> 1952

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 7900
   - **Unique Online Proxies** -> 7005
   - **Unique Online/Offline Proxies (Archive)** -> 31071

## [SOCKS4 (3841/7005)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.2.203.198:4145
1.2.214.154:4145
1.4.195.114:4145
1.4.214.148:5678
1.9.71.4:4153
1.9.167.35:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:37718
1.20.95.95:5678
1.20.137.82:32241
1.20.168.236:4145
1.20.198.8:4153
1.32.57.85:5678
1.179.147.5:52210
1.179.148.9:36476
1.179.172.45:31225
1.179.173.114:4153
1.179.181.213:30500
1.186.40.9:39651
1.186.40.157:39651
1.186.139.9:39651
1.212.181.131:4145
1.220.145.45:4145
2.87.204.44:4145
2.139.162.80:4145
2.179.254.169:5678
```

## [SOCKS5 (322/7005)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:1080
1.65.139.83:1080
3.36.98.199:9050
3.234.216.105:1080
5.42.158.11:1080
5.42.158.108:1080
5.42.158.119:1080
5.42.158.126:1080
5.56.134.237:45698
5.105.1.86:16379
8.210.179.3:25170
8.210.251.244:6655
13.250.172.147:48540
13.251.43.206:48540
13.251.59.142:48540
13.251.124.20:48540
13.251.127.63:48540
18.141.180.11:1080
18.181.146.180:1088
18.228.138.55:5555
20.198.168.89:1080
23.94.149.131:53335
24.249.199.12:4145
27.16.214.34:1080
27.116.51.92:6667
27.116.51.119:6667
27.116.51.178:6667
27.254.149.244:9050
31.128.248.2:1080
34.101.112.42:1080
```

## [HTTP (1785/7005)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.1.220.100:8080
1.2.252.65:8080
1.10.188.78:45208
1.14.104.146:808
1.20.166.142:8080
1.32.59.217:47045
1.52.246.49:10003
1.52.246.51:10001
1.117.100.196:7788
1.179.136.98:8080
1.179.144.41:8080
1.179.183.73:50178
2.179.193.146:80
2.188.166.22:3128
3.20.236.208:49205
3.94.93.17:49205
3.135.231.173:49205
3.215.177.148:49205
5.16.0.49:8080
5.16.0.77:1256
5.16.0.174:8080
5.20.91.12:60792
5.26.96.212:8080
5.34.153.142:8080
5.42.158.11:11111
5.44.54.106:8080
5.58.58.209:8080
5.59.136.230:8080
5.130.90.3:8080
```

## [HTTPS (1952/7005)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.163.172:8081
1.0.205.87:8080
1.14.104.146:808
1.20.217.52:8080
1.32.59.217:47045
1.52.246.49:10003
1.117.100.196:7788
1.179.136.98:8080
1.179.144.41:8080
1.179.183.73:50178
1.225.178.185:8080
2.184.4.68:6565
2.184.4.70:6565
2.188.166.26:3128
3.17.142.21:49205
3.94.93.17:49205
3.135.231.173:49205
3.235.197.149:49205
5.16.0.77:1256
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.26.96.212:8080
5.34.153.142:8080
5.58.33.187:55507
5.59.136.230:8080
5.130.90.3:8080
5.131.243.11:8080
5.133.24.25:8080
5.133.27.61:3129
```

## [ARCHIVE (7005/31071)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.141.90:4145
1.0.145.246:4145
1.0.147.198:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.154.141:4145
1.0.163.85:4145
1.0.163.172:8081
1.0.170.50:8080
1.0.205.87:8080
1.0.213.133:8080
1.0.239.61:5678
1.0.243.247:4145
1.0.245.18:4145
1.1.128.155:5678
1.1.129.166:4145
1.1.167.139:4145
1.1.187.209:5678
1.1.187.210:4145
1.1.189.58:8080
1.1.214.117:8081
1.1.220.100:8080
1.1.227.53:4145
1.1.227.187:4145
1.1.227.254:4145
1.1.229.44:4145
1.1.235.90:5678
```



Thx Co Pure Gs - Sort Meister! 💟