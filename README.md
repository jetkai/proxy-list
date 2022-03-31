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

# [SAMPLE PROXIES] - [March 31 2022 | 09:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1409
   - **SOCKS5** -> 135
   - **HTTP** -> 295
   - **HTTPS** -> 206

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2045
   - **Unique Online Proxies** -> 1971
   - **Unique Online/Offline Proxies (Archive)** -> 13141

## [SOCKS4 (1409/1971)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.214.148:5678
1.9.164.242:35471
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.141.220:37718
1.53.137.84:4145
1.55.241.4:4145
1.179.148.9:36476
1.179.151.165:31948
1.186.46.36:5678
2.87.206.72:4145
2.135.223.134:5678
3.141.13.98:5678
4.28.96.169:39593
5.22.154.50:32127
5.58.47.25:3629
5.58.53.216:1085
5.58.66.55:14888
5.152.175.13:2580
5.160.39.219:3629
5.172.188.92:5678
5.172.188.93:5678
5.178.217.227:31019
5.180.100.24:5678
5.190.60.221:3629
8.39.228.5:39593
8.39.228.113:39593
8.39.228.161:39593
8.42.68.17:39593
```

## [SOCKS5 (135/1971)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.49.222:7302
5.11.17.230:1080
14.23.50.42:7302
24.249.199.4:4145
24.249.199.12:4145
27.116.51.119:6667
31.128.248.2:1080
43.129.77.148:3001
43.129.243.128:3001
43.224.8.116:6667
43.224.10.13:6667
43.224.10.26:6667
43.224.10.27:6667
43.224.10.32:6667
43.224.10.35:6667
43.224.10.36:6667
43.224.10.46:6667
43.224.10.48:6667
45.81.129.176:8888
45.142.212.10:30003
45.142.212.10:30001
46.101.5.73:48528
46.147.194.197:1080
50.63.165.21:23859
54.38.110.231:48325
58.18.36.61:7302
58.21.199.78:7302
60.10.10.171:7302
60.12.77.43:7300
60.165.35.64:7302
```

## [HTTP (295/1971)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.179.144.41:8080
1.186.245.226:1111
5.160.91.130:3128
5.189.186.24:5566
5.202.191.226:8080
14.139.184.130:3128
14.170.154.10:8080
14.192.3.161:84
14.239.65.212:19132
24.43.140.138:8080
36.66.16.193:8080
36.89.212.251:8080
36.91.98.115:8181
36.91.166.98:8080
36.95.27.209:80
36.95.79.7:41890
36.95.156.125:6969
36.95.207.233:8080
37.232.183.74:53281
41.60.232.125:34098
41.72.203.182:42928
41.84.152.241:8080
41.86.42.41:8080
41.204.87.90:8080
41.216.178.151:8080
41.254.53.70:1976
43.224.8.116:6666
43.224.10.33:6666
43.224.10.43:6666
```

## [HTTPS (206/1971)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
5.16.0.180:8080
5.104.174.199:23500
5.149.219.201:8080
5.189.186.24:5566
8.208.91.118:3128
14.139.184.130:3128
27.116.51.85:6666
27.121.85.74:8080
36.66.172.121:39810
36.89.212.250:8080
36.94.183.153:8080
36.95.120.101:41890
36.95.156.125:6969
39.108.56.233:8080
41.33.86.242:8080
43.242.242.196:8080
45.121.216.218:55443
45.176.95.100:999
45.181.206.1:999
45.184.129.165:8181
45.224.153.39:999
45.229.34.101:999
45.251.74.228:80
46.52.180.194:8080
49.0.39.186:8080
50.192.250.60:8080
50.233.42.98:51696
50.236.203.15:8080
51.68.199.120:3128
51.79.50.22:9300
```

## [ARCHIVE (1971/13141)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
```



Thx Co Pure Gs - Sort Meister! 💟