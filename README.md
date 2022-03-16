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

# [SAMPLE PROXIES] - [March 16 2022 | 03:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 798
   - **SOCKS5** -> 130
   - **HTTP** -> 448
   - **HTTPS** -> 273

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1649
   - **Unique Online Proxies** -> 1542
   - **Unique Online/Offline Proxies (Archive)** -> 6873

## [SOCKS4 (798/1542)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.9.167.35:60489
1.20.184.75:4153
1.179.130.201:4153
1.179.186.71:1080
1.186.40.2:39651
1.186.213.67:5678
2.183.8.145:4153
5.58.47.25:3629
5.172.188.93:5678
5.190.60.221:3629
8.39.228.21:39593
8.40.133.10:1099
8.42.71.224:39593
12.158.87.26:39593
12.187.55.1:39593
13.58.223.158:5678
14.102.19.50:5678
14.248.80.34:5678
18.188.253.82:5555
18.216.32.60:5678
24.249.199.12:4145
27.116.51.85:6667
27.131.168.137:5678
27.147.131.219:50391
27.147.241.134:10800
31.41.225.205:45067
31.170.19.233:4153
31.172.133.253:4153
31.182.13.17:34715
31.206.38.46:37630
```

## [SOCKS5 (130/1542)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
23.94.122.39:53783
34.95.224.52:443
39.152.104.167:7300
43.128.36.71:3389
43.224.10.27:6667
43.224.10.42:6667
45.67.229.104:30003
45.142.212.31:30003
47.109.40.23:1080
49.51.69.212:21127
49.51.74.61:21127
50.63.165.21:23859
51.38.32.239:31779
51.83.21.224:16379
58.21.199.78:7302
58.222.132.163:7302
59.59.6.86:7300
60.10.37.21:7302
60.12.109.74:7302
60.12.215.23:7302
60.28.57.177:7302
60.215.109.34:7302
61.54.227.70:7302
61.130.151.230:7302
61.153.42.218:7302
61.178.172.95:7302
62.113.115.94:16072
70.185.68.133:4145
72.195.34.41:4145
72.195.34.42:4145
```

## [HTTP (448/1542)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.4.198.22:8081
1.20.217.52:8080
1.179.136.98:8080
1.179.148.9:55636
1.186.245.226:80
3.20.236.208:49205
3.215.177.148:49205
5.58.33.187:55507
5.180.130.90:8080
5.180.130.91:80
8.214.41.50:80
8.242.207.202:8080
12.31.246.5:8080
12.88.29.66:9080
14.139.184.130:3128
14.143.172.238:8080
14.170.154.10:8080
14.207.122.162:8080
18.216.72.10:49205
18.222.17.49:49205
24.113.42.177:48678
31.3.169.53:8081
31.163.192.161:3129
31.210.171.77:8080
36.66.103.211:3128
36.66.172.121:39810
36.91.45.10:51672
36.91.166.98:8080
36.92.165.91:8080
36.95.34.106:8080
```

## [HTTPS (273/1542)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.20.217.52:8080
1.179.144.41:8080
3.20.236.208:49205
14.102.40.97:83
14.139.184.130:3128
14.192.3.161:82
18.216.72.10:49205
18.216.136.190:9090
18.222.17.49:49205
27.147.209.215:8080
31.3.169.53:8081
31.42.57.1:8080
34.229.130.62:49205
34.230.89.25:49205
36.80.51.175:8080
36.92.134.71:999
36.95.156.127:6969
38.130.248.181:999
41.65.67.166:1981
41.77.129.154:53281
41.87.165.222:3128
41.184.92.24:8080
41.190.11.94:8080
41.203.83.66:8080
43.129.223.147:38080
43.224.8.14:6666
43.224.10.27:6666
45.5.92.94:8137
45.114.38.57:8080
45.167.95.184:8085
```

## [ARCHIVE (1542/6873)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.170.50:8080
1.1.169.159:4145
1.1.189.58:8080
1.2.187.252:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.195.114:4145
1.4.198.22:8081
1.4.214.148:5678
1.9.27.217:4153
1.9.167.35:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.10.189.133:50855
1.20.96.30:4153
1.20.96.156:4153
1.20.184.75:4153
1.20.217.52:8080
1.32.59.217:31981
1.32.59.217:47045
1.53.137.84:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.136.98:8080
1.179.144.41:8080
1.179.147.5:52210
1.179.148.9:36476
```



Thx Co Pure Gs - Sort Meister! 💟