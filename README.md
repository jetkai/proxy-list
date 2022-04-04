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

# [SAMPLE PROXIES] - [April 04 2022 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 668
   - **SOCKS5** -> 112
   - **HTTP** -> 305
   - **HTTPS** -> 202

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1287
   - **Unique Online Proxies** -> 1215
   - **Unique Online/Offline Proxies (Archive)** -> 13993

## [SOCKS4 (668/1215)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.182.209:4145
1.10.140.43:4145
1.10.189.133:50855
1.20.95.95:5678
1.20.137.82:32241
1.20.184.75:4153
1.179.151.165:31948
1.179.186.70:1080
1.186.46.36:5678
1.186.82.4:5678
2.183.8.145:4153
5.22.154.50:32127
5.130.72.170:5678
5.135.24.186:808
5.152.175.13:2580
5.153.140.180:4145
5.180.100.24:5678
5.188.211.54:7777
5.189.152.82:1080
5.190.60.221:3629
8.42.69.93:39593
8.42.69.105:39593
13.58.88.184:5678
13.58.223.158:5678
14.181.7.187:5678
14.232.161.29:10801
14.232.166.150:5678
14.241.241.185:4145
18.144.166.125:63999
18.216.32.60:5678
```

## [SOCKS5 (112/1215)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
23.234.213.157:6666
24.249.199.4:4145
24.249.199.12:4145
31.128.248.1:1080
37.131.202.95:33427
39.165.98.152:7302
43.224.10.46:6667
47.240.226.173:1080
50.63.165.21:23859
50.63.165.21:16870
51.83.21.224:16379
58.18.36.61:7302
58.21.199.78:7302
58.221.186.107:7302
60.10.10.171:7302
60.12.72.206:7300
60.12.215.23:7302
60.215.109.34:7302
61.50.105.202:7300
61.90.185.170:7302
61.132.47.18:54191
61.135.155.82:1080
61.153.62.163:7302
61.178.99.43:7302
61.178.172.95:7302
61.178.172.95:7300
61.182.207.98:7302
61.191.149.44:7302
62.128.111.250:443
67.201.33.10:25283
```

## [HTTP (305/1215)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.179.148.9:55636
1.186.40.35:1111
1.186.245.226:80
5.16.1.17:8080
36.66.16.193:80
36.67.150.247:8080
36.91.148.37:8080
36.92.165.91:8080
36.94.183.153:8080
36.95.53.227:8080
36.95.54.114:8080
36.95.65.99:8019
36.95.84.151:41890
36.95.156.125:6969
36.95.249.157:8080
37.187.121.221:1081
37.235.24.194:3128
39.106.228.34:8082
39.108.56.233:38080
41.86.42.41:8080
43.224.10.13:6666
43.224.10.30:6666
43.250.127.98:9001
45.6.103.149:8080
45.32.83.231:3128
45.43.63.230:10001
45.71.203.106:999
45.169.163.73:999
45.169.163.225:999
45.172.108.42:999
```

## [HTTPS (202/1215)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
5.35.38.8:32132
8.214.41.50:80
27.42.168.46:55481
27.123.4.106:8181
31.42.57.1:8080
34.229.130.62:49205
36.37.160.242:8080
36.94.56.90:8080
36.94.199.131:8080
36.95.34.106:8080
41.94.107.2:8080
41.180.68.195:8080
41.180.106.6:8080
41.184.178.247:8080
41.216.68.254:41890
41.254.53.70:1981
43.243.174.3:82
43.249.224.172:83
45.5.68.25:999
45.32.83.231:3128
45.65.132.148:8080
45.175.160.34:999
45.229.34.101:999
46.19.100.26:81
46.52.180.194:8080
50.232.250.157:8080
61.216.156.222:60808
62.75.229.77:5566
62.75.229.155:5566
62.75.229.167:5566
```

## [ARCHIVE (1215/13993)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.4.161.108:4145
1.4.182.209:4145
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
```



Thx Co Pure Gs - Sort Meister! 💟