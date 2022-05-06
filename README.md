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

# [SAMPLE PROXIES] - [May 06 2022 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1457
   - **SOCKS5** -> 217
   - **HTTP** -> 382
   - **HTTPS** -> 346

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2402
   - **Unique Online Proxies** -> 2289
   - **Unique Online/Offline Proxies (Archive)** -> 19910

## [SOCKS4 (1457/2289)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.89:4153
1.2.212.222:4145
1.4.195.114:4145
1.9.213.114:4153
1.20.95.95:5678
1.20.96.164:4153
1.20.137.82:32241
1.20.184.75:4153
1.20.227.66:4145
1.179.130.201:4153
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.186.40.177:39651
2.50.19.23:4145
3.141.13.98:5678
5.22.154.50:32127
5.32.181.188:56002
5.34.74.234:5678
5.39.93.167:21544
5.44.254.70:4145
5.58.47.25:3629
5.58.53.216:1085
5.152.175.13:2580
5.160.81.157:4145
5.165.2.223:3629
5.178.217.227:31019
5.180.100.24:5678
5.181.248.202:5678
5.202.159.63:5678
```

## [SOCKS5 (217/2289)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.21.26:33080
1.71.170.146:7302
3.19.179.179:8000
13.233.84.6:39998
14.149.69.217:7300
24.249.199.12:4145
27.128.206.18:7302
31.25.92.5:44949
31.43.203.100:1080
36.35.240.26:7302
39.106.85.163:7891
43.129.243.128:3001
43.134.100.47:32187
43.224.10.11:6667
43.224.10.30:6667
43.224.10.31:6667
43.224.10.32:6667
43.224.10.37:6667
45.132.236.249:8888
46.101.5.73:45199
46.146.227.89:1080
46.147.194.197:1080
47.52.254.9:9100
47.240.226.173:1080
49.232.140.41:1080
50.63.165.21:23859
51.83.190.248:19050
51.155.3.184:33427
51.255.71.43:1080
52.0.40.116:1080
```

## [HTTP (382/2289)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.186.85.38:1111
3.20.236.208:49205
3.215.177.148:49205
5.56.133.132:3128
5.59.136.230:8080
5.101.98.235:3128
12.144.254.185:9080
14.20.235.19:45770
14.20.235.21:808
18.216.72.10:49205
18.222.17.49:49205
24.116.218.195:8080
27.111.45.25:55443
27.147.193.82:8080
31.128.71.241:8081
36.91.98.115:8181
36.92.70.209:8080
36.92.93.61:8080
36.94.161.219:8080
36.95.81.251:41890
36.95.156.127:6969
37.1.37.216:53281
37.26.136.181:52271
37.131.202.95:41890
37.252.73.192:8080
38.123.68.152:999
41.77.13.186:53281
41.84.141.14:8080
41.84.146.179:8080
41.86.42.41:8080
```

## [HTTPS (346/2289)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
1.0.170.50:80
1.4.198.22:8081
1.186.85.114:1111
3.19.179.179:8000
3.20.236.208:49205
3.215.177.148:49205
5.188.136.52:8080
5.189.229.42:1081
12.90.37.182:8181
14.160.29.90:8080
18.216.72.10:49205
18.222.17.49:49205
24.172.34.114:49920
27.116.51.119:8080
34.229.130.62:49205
34.230.89.25:49205
36.67.237.146:3128
36.89.212.251:8080
36.92.93.61:8080
36.93.75.154:8080
36.95.53.227:8080
36.95.156.125:6969
36.95.156.127:6969
36.95.249.157:8080
37.1.37.216:53281
37.131.202.95:41890
37.204.157.91:41890
37.235.24.194:3128
41.59.200.20:9999
```

## [ARCHIVE (2289/19910)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.197:4145
1.0.137.61:4153
1.0.148.135:4145
1.0.149.73:4145
1.0.152.183:4145
1.0.154.38:4145
1.0.161.25:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.208.93:4145
1.0.213.104:4145
1.0.224.88:4145
1.0.232.127:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.228.123:4145
1.1.228.201:4145
1.1.244.19:4145
1.2.182.57:4145
1.2.182.121:4145
1.2.187.19:4145
1.2.187.250:4145
1.2.187.252:4145
1.2.202.204:3629
```



Thx Co Pure Gs - Sort Meister! 💟