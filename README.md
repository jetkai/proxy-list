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

# [SAMPLE PROXIES] - [May 18 2022 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1666
   - **SOCKS5** -> 183
   - **HTTP** -> 350
   - **HTTPS** -> 319

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2518
   - **Unique Online Proxies** -> 2389
   - **Unique Online/Offline Proxies (Archive)** -> 21553

## [SOCKS4 (1666/2389)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.0.154.166:4145
1.1.161.243:4145
1.2.180.111:4145
1.4.157.35:36202
1.10.140.43:4145
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.184.75:4153
1.20.220.79:4145
1.55.241.4:4145
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.186.68:1080
1.186.139.9:39651
1.186.213.67:5678
1.221.173.148:4145
2.57.8.76:4153
2.139.162.80:4145
3.141.13.98:5678
4.14.120.234:39593
5.1.104.66:33041
5.34.74.234:5678
5.58.47.25:3629
5.135.24.186:808
5.160.81.157:4145
5.172.188.90:5678
5.178.204.235:2082
```

## [SOCKS5 (183/2389)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.19.179.179:8000
5.161.100.145:1080
5.189.148.7:39299
5.189.229.42:1080
18.136.106.96:8081
18.189.228.38:8000
24.249.199.4:4145
24.249.199.12:4145
27.116.51.119:6667
31.25.92.5:44949
31.128.248.1:1080
31.128.248.2:1080
36.35.240.26:7302
43.128.7.195:1080
43.224.10.48:6667
46.101.5.73:43639
46.101.5.73:45199
46.101.5.73:46999
46.101.5.73:47981
47.240.226.173:1080
50.63.165.21:23859
51.75.195.157:37606
51.79.52.80:3080
51.155.3.184:33427
51.254.44.184:45904
52.28.99.91:1080
58.18.36.61:7302
59.47.140.142:7300
59.47.140.142:7302
59.98.82.114:1080
```

## [HTTP (350/2389)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.13.165.87:8080
1.13.165.87:33080
3.20.236.208:49205
3.215.177.148:49205
5.167.141.239:3128
5.189.229.42:1081
5.202.191.226:8080
14.192.2.161:83
18.216.72.10:49205
18.222.17.49:49205
31.171.154.199:8118
34.101.127.131:8080
36.66.172.121:39810
36.89.49.55:8181
36.92.109.146:8080
36.93.30.197:8080
36.94.2.138:443
36.94.47.58:4480
36.94.98.146:8080
36.94.199.131:8080
36.95.79.7:41890
36.95.116.9:9812
38.130.249.129:999
38.130.249.137:999
41.33.86.242:8080
41.60.235.140:8080
41.60.236.234:34098
41.193.63.89:8080
43.129.223.147:38080
```

## [HTTPS (319/2389)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.189.58:8080
1.13.165.87:33080
1.186.85.38:80
1.186.85.38:1111
2.179.193.146:80
3.20.236.208:49205
3.215.177.148:49205
5.56.133.132:3128
14.160.29.90:8080
14.231.193.206:19132
18.189.228.38:8000
18.216.72.10:49205
18.222.17.49:49205
24.172.82.94:53281
34.229.130.62:49205
34.230.89.25:49205
36.66.124.193:3128
36.67.150.247:8080
36.91.98.115:8181
36.92.109.146:8080
36.92.134.71:999
36.94.17.138:8080
36.95.81.251:41890
36.95.207.233:8080
37.252.73.193:8080
41.60.216.56:23500
41.65.162.75:1981
41.77.188.178:80
41.79.64.202:8001
41.193.63.89:8080
```

## [ARCHIVE (2389/21553)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.197:4145
1.0.136.217:4145
1.0.137.61:4153
1.0.148.135:4145
1.0.149.73:4145
1.0.151.157:4145
1.0.152.183:4145
1.0.154.38:4145
1.0.154.166:4145
1.0.159.150:4145
1.0.160.238:4145
1.0.161.25:4145
1.0.161.232:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.208.93:4145
1.0.213.104:4145
1.0.224.88:4145
1.0.232.127:4145
1.1.161.243:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.228.123:4145
1.1.228.201:4145
```



Thx Co Pure Gs - Sort Meister! 💟