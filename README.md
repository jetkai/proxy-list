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

# [SAMPLE PROXIES] - [March 31 2022 | 03:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1308
   - **SOCKS5** -> 135
   - **HTTP** -> 342
   - **HTTPS** -> 229

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2014
   - **Unique Online Proxies** -> 1937
   - **Unique Online/Offline Proxies (Archive)** -> 12932

## [SOCKS4 (1308/1937)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.4.157.35:36202
1.4.214.148:5678
1.9.27.217:4153
1.9.164.242:35471
1.9.167.35:60489
1.10.140.43:4145
1.20.95.95:5678
1.20.96.156:4153
1.20.184.75:4153
1.20.227.66:4145
1.32.59.217:31981
1.186.40.9:39651
1.212.157.115:4145
2.87.206.72:4145
2.139.162.80:4145
2.197.124.172:4153
3.141.13.98:5678
4.14.120.234:39593
4.28.96.254:39593
5.1.104.66:33041
5.34.74.234:5678
5.58.47.25:3629
5.58.66.55:14888
5.104.184.59:5678
5.141.86.233:60705
5.152.170.73:8899
5.172.188.92:5678
5.172.188.93:5678
5.178.193.43:1080
```

## [SOCKS5 (135/1937)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:8080
5.144.135.117:1080
14.23.50.42:7302
23.234.213.157:6666
24.249.199.4:4145
24.249.199.12:4145
31.211.131.136:33427
37.139.243.32:1080
39.152.104.167:7302
39.184.147.250:7302
43.224.10.36:6667
43.224.10.42:6667
43.224.10.46:6667
45.67.229.101:30003
45.144.29.248:8080
50.63.165.21:16870
51.222.13.193:10084
54.38.110.231:48325
58.18.36.61:7302
58.21.199.78:7302
58.217.115.142:7302
60.10.37.21:7302
60.12.77.43:7300
60.12.215.23:7302
60.165.35.64:7302
60.215.109.34:7302
61.132.47.18:54191
61.133.8.86:7302
61.153.62.163:7302
61.174.68.160:7302
```

## [HTTP (342/1937)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.220.100:8080
1.20.217.52:8080
1.179.144.41:8080
2.188.166.26:3128
3.215.177.148:49205
5.16.1.17:8080
5.104.174.199:23500
8.208.91.118:80
12.218.209.130:53281
24.113.42.177:48678
31.173.94.93:43539
34.94.137.131:80
36.66.242.146:43936
36.94.61.196:4480
36.95.21.92:8080
36.255.86.114:83
38.10.246.142:9991
41.204.87.90:8080
43.224.10.26:6666
43.224.10.33:6666
43.224.10.35:6666
45.5.92.94:8137
45.32.83.231:3128
45.127.56.194:84
45.133.245.159:3128
45.167.72.22:8080
45.169.148.2:999
45.169.148.11:999
45.169.148.19:999
45.174.87.18:999
```

## [HTTPS (229/1937)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.10.141.220:54620
1.186.85.38:1111
2.184.4.70:6565
2.188.166.25:3128
8.208.91.118:8800
8.214.41.50:80
14.160.29.90:8080
23.234.213.157:6666
27.147.209.215:8080
35.187.224.178:3128
36.67.27.189:39674
36.67.168.117:8080
36.92.22.70:8080
36.92.116.26:8080
36.93.2.50:8080
36.94.17.138:8080
36.95.54.114:8080
36.95.120.101:41890
36.95.156.125:6969
38.101.122.186:999
41.203.83.66:8080
41.254.53.70:1976
43.224.8.12:6666
43.252.10.146:2222
45.5.57.122:8080
45.5.68.33:999
45.5.94.178:3128
45.81.144.51:8080
45.156.31.4:9090
45.156.31.16:9090
```

## [ARCHIVE (1937/12932)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.137.61:4153
1.0.154.38:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.224.88:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.244.19:4145
1.2.182.57:4145
1.2.187.250:4145
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
```



Thx Co Pure Gs - Sort Meister! 💟