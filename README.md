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

# [SAMPLE PROXIES] - [May 29 2022 | 05:49:48]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1491
   - **SOCKS5** -> 250
   - **HTTP** -> 313
   - **HTTPS** -> 246

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2006
   - **Unique Online Proxies** -> 2006
   - **Unique Online/Offline Proxies (Archive)** -> 2006

## [SOCKS4 (1491/2006)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.89:4153
1.9.167.35:60489
1.9.167.36:60489
1.10.133.211:4145
1.20.96.30:4153
1.20.96.164:4153
1.20.184.75:4153
1.20.220.79:4145
1.32.57.85:5678
1.179.148.9:36476
1.179.151.165:31948
1.186.85.74:5678
2.57.8.76:4153
3.120.173.144:8080
3.141.13.98:5678
3.211.17.212:80
5.8.240.90:4153
5.8.240.91:4153
5.34.74.234:5678
5.44.254.40:4145
5.58.53.216:1085
5.161.93.53:1080
5.172.188.90:5678
5.178.204.235:2082
5.178.217.227:31019
5.180.100.24:5678
5.201.178.102:5678
8.17.28.139:39593
8.39.228.25:39593
8.39.228.33:39593
```

## [SOCKS5 (250/2006)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.19.179.179:8000
3.120.173.144:8080
3.131.207.170:13343
3.211.17.212:80
5.161.86.206:1080
5.161.100.145:1080
5.189.186.24:5566
5.253.145.247:1080
8.218.69.97:8000
8.218.109.21:443
12.151.56.30:80
13.233.84.6:39998
18.206.33.119:8888
20.222.136.61:8000
20.230.193.232:80
24.249.199.4:4145
24.249.199.12:4145
27.128.196.205:7302
31.25.92.5:44949
35.244.6.175:1080
36.7.108.56:9091
36.35.240.26:7302
37.18.73.94:5566
37.192.253.250:1080
39.175.75.8:30001
39.175.92.205:30001
43.128.7.195:1080
43.128.36.71:3389
43.129.207.123:3001
43.132.203.188:57890
```

## [HTTP (313/2006)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.209.28:8080
3.19.179.179:8000
3.20.236.208:49205
3.215.177.148:49205
5.104.174.199:23500
14.177.235.17:8080
18.216.72.10:5678
18.222.17.49:49205
20.203.120.85:80
27.105.130.93:8080
36.66.172.121:39810
36.67.151.11:80
36.92.92.226:8080
36.93.2.50:8080
38.130.249.137:999
43.132.197.151:443
43.154.71.147:8118
43.224.10.30:6667
43.254.132.123:8118
45.7.135.238:999
45.153.165.118:999
45.167.125.209:9992
45.167.253.129:999
45.170.100.10:999
45.174.176.151:8085
45.175.160.141:999
45.184.73.114:40033
45.189.117.237:999
45.190.249.100:8080
45.191.196.254:999
```

## [HTTPS (246/2006)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
3.20.236.208:49205
3.215.177.148:49205
5.104.174.199:23500
5.135.176.161:10000
14.1.102.41:3127
14.102.40.97:83
14.177.235.17:8080
14.207.145.80:9080
18.216.72.10:5678
18.222.17.49:49205
24.106.221.230:53281
24.116.218.195:8080
27.131.179.197:10443
34.229.130.62:49205
34.230.89.25:49205
36.66.172.121:39810
36.67.152.213:11111
36.93.2.50:8080
36.94.54.93:9812
37.252.73.192:8080
41.77.13.186:53281
41.242.116.235:50000
42.192.22.233:8118
43.224.10.30:6667
43.224.10.43:6666
43.254.132.123:8118
45.70.15.5:8080
45.81.144.51:8080
45.153.165.118:999
45.190.249.100:8080
```

## [ARCHIVE (2006/2006)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.133.89:4153
1.9.167.35:60489
1.9.167.36:60489
1.10.133.211:4145
1.20.96.30:4153
1.20.96.164:4153
1.20.184.75:4153
1.20.209.28:8080
1.20.220.79:4145
1.32.57.85:5678
1.179.148.9:36476
1.179.151.165:31948
1.186.85.74:5678
2.57.8.76:4153
3.19.179.179:8000
3.20.236.208:49205
3.120.173.144:8080
3.131.207.170:13343
3.141.13.98:5678
3.211.17.212:80
3.215.177.148:49205
5.8.240.90:4153
5.8.240.91:4153
5.34.74.234:5678
5.44.254.40:4145
5.58.53.216:1085
5.104.174.199:23500
5.135.176.161:10000
5.161.86.206:1080
5.161.93.53:1080
```



Thx Co Pure Gs - Sort Meister! 💟