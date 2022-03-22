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

# [SAMPLE PROXIES] - [March 22 2022 | 07:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 798
   - **SOCKS5** -> 78
   - **HTTP** -> 539
   - **HTTPS** -> 334

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1749
   - **Unique Online Proxies** -> 1677
   - **Unique Online/Offline Proxies (Archive)** -> 11586

## [SOCKS4 (798/1677)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.214.148:5678
1.9.213.114:4153
1.179.148.9:36476
1.179.151.165:31948
1.179.173.114:4153
1.186.213.67:5678
2.183.8.145:4153
3.141.13.98:5678
4.14.120.230:39593
5.133.24.167:5678
5.141.86.233:60705
5.166.57.222:49710
5.172.188.93:5678
5.189.148.7:13862
5.200.81.230:5678
8.40.133.10:1099
8.42.69.93:39593
8.42.69.105:39593
12.11.59.114:1080
12.216.103.114:39072
13.58.88.184:5678
13.58.223.158:5678
14.102.78.67:4145
14.102.101.254:4153
14.142.20.134:4145
14.207.146.33:5678
14.232.160.247:10801
18.216.32.60:5678
18.216.72.10:5678
24.88.66.70:64312
```

## [SOCKS5 (78/1677)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.131.207.170:13343
27.116.51.85:6667
37.131.202.95:33427
43.224.10.8:6667
45.142.212.10:30003
46.101.5.73:48528
47.109.40.23:1080
51.83.21.224:16379
58.18.36.61:7302
59.47.140.142:7302
60.10.37.21:7302
60.12.72.206:7300
60.174.107.73:7302
60.215.109.34:7302
61.135.30.54:7302
61.175.220.11:7302
61.178.94.23:7302
61.191.149.44:7302
62.113.115.94:16072
68.71.249.153:48606
84.238.219.216:33427
85.172.31.16:33427
91.142.172.7:5678
92.222.206.150:2468
92.222.206.151:18979
93.190.141.62:9050
103.216.82.37:6667
103.230.212.21:7302
103.240.168.138:6667
103.241.227.107:6667
```

## [HTTP (539/1677)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.166.142:8080
1.179.148.9:55636
1.186.245.226:80
2.188.166.26:3128
5.16.1.17:8080
5.35.38.8:32132
5.58.33.187:55507
5.104.174.199:23500
5.139.161.156:55443
5.202.191.226:8080
8.214.41.50:80
8.242.207.164:999
14.139.184.130:3128
14.160.29.90:8080
14.161.252.185:55443
14.170.154.10:8080
14.192.3.161:82
14.241.39.165:19132
18.191.253.100:49205
18.216.72.10:49205
18.222.17.49:49205
24.43.140.138:8080
27.105.130.93:8080
27.111.45.25:55443
31.3.169.45:8080
31.173.94.93:43539
34.101.127.131:8080
36.66.19.10:8080
36.66.172.121:39810
36.66.242.146:43936
```

## [HTTPS (334/1677)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.2.252.65:8080
2.184.4.70:6565
3.20.236.208:49205
5.16.0.180:8080
5.131.243.10:8080
5.202.191.226:8080
14.160.29.90:8080
18.191.253.100:49205
27.42.168.46:55481
27.255.3.134:3128
31.128.71.241:8081
31.131.67.14:8080
31.173.94.93:43539
34.229.130.62:49205
36.37.81.135:8080
36.37.160.242:8080
36.66.19.10:8080
36.67.118.207:8080
36.67.237.146:3128
36.92.70.209:8080
36.94.161.219:8080
36.95.21.92:8080
37.232.183.74:53281
38.123.68.152:999
41.190.11.94:8080
43.243.140.194:8080
43.243.140.198:8080
43.243.172.2:83
43.249.224.170:83
45.5.57.122:8080
```

## [ARCHIVE (1677/11586)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.154.38:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.2.182.57:4145
1.2.187.252:4145
1.2.222.252:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.195.114:4145
1.4.198.22:8081
1.4.214.148:5678
1.9.27.217:4153
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.133.19:4145
1.10.140.43:4145
1.10.141.220:37718
1.10.141.220:54620
1.10.189.133:50855
1.13.165.87:8080
1.20.95.95:5678
1.20.96.30:4153
```



Thx Co Pure Gs - Sort Meister! 💟