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

# [SAMPLE PROXIES] - [May 23 2022 | 05:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1058
   - **SOCKS5** -> 153
   - **HTTP** -> 403
   - **HTTPS** -> 339

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1953
   - **Unique Online Proxies** -> 1823
   - **Unique Online/Offline Proxies (Archive)** -> 22041

## [SOCKS4 (1058/1823)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.154.166:4145
1.1.161.243:4145
1.9.213.114:4153
1.20.96.164:4153
1.20.227.66:4145
1.32.57.85:5678
1.165.109.132:3629
1.179.151.165:31948
1.179.186.71:1080
1.186.40.157:39651
1.186.139.9:39651
1.220.145.45:4145
1.221.173.148:4145
3.141.13.98:5678
5.8.240.90:4153
5.34.74.234:5678
5.58.47.25:3629
5.58.66.55:14888
5.139.58.214:4145
5.152.175.13:2580
5.172.188.92:5678
5.178.204.235:2082
5.178.217.227:31019
5.190.60.221:3629
8.42.68.93:39593
12.7.109.227:39593
12.11.59.114:1080
12.158.87.26:39593
12.187.55.1:39593
12.218.209.130:13326
```

## [SOCKS5 (153/1823)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.71.170.146:7302
1.180.49.222:7302
3.130.56.109:8000
5.161.93.53:1080
5.161.100.145:1080
13.233.84.6:39998
18.136.106.96:8081
24.249.199.4:4145
24.249.199.12:4145
31.128.248.1:1080
31.184.220.67:1080
36.35.240.26:7302
36.89.86.49:56845
37.18.73.60:5566
37.187.72.171:22807
43.128.7.195:1080
43.129.207.123:3001
43.135.74.226:38081
43.224.10.11:6667
45.10.69.98:8888
45.55.182.183:51142
51.83.190.248:19050
51.155.3.184:33427
51.254.44.184:60677
54.38.242.224:22272
58.22.60.174:1080
59.47.140.142:7302
59.47.140.142:7300
59.98.82.114:1080
60.12.77.43:7300
```

## [HTTP (403/1823)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.2.252.65:8080
1.186.85.2:1111
3.20.236.208:49205
3.128.120.252:80
3.215.177.148:49205
5.16.0.174:8080
5.202.191.226:8080
12.88.29.66:9080
12.218.209.130:53281
14.170.154.193:19132
14.192.3.161:84
14.231.193.206:19132
18.222.17.49:49205
27.131.179.206:10443
31.128.71.241:8081
31.171.154.199:8118
36.66.124.193:3128
36.66.172.121:39810
36.67.27.189:39674
36.67.168.117:8080
36.91.108.141:3128
36.92.70.209:8080
36.92.140.113:8080
36.95.34.108:9812
37.232.183.74:53281
38.41.53.144:9090
38.130.249.129:999
38.130.249.137:999
41.65.67.166:1981
```

## [HTTPS (339/1823)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.186.40.35:1111
3.20.236.208:49205
3.128.120.252:80
3.215.177.148:49205
5.167.141.239:3128
14.20.235.19:45770
14.241.39.191:8080
18.216.72.10:49205
18.222.17.49:49205
27.131.179.204:10443
27.131.179.220:10443
34.229.130.62:49205
34.230.89.25:49205
36.67.27.189:39674
36.67.168.117:8080
36.67.237.146:3128
36.93.6.170:8080
36.94.2.138:443
36.94.40.123:9812
36.94.47.59:4480
36.95.54.114:8080
36.95.156.127:6969
41.161.92.138:8080
41.190.147.158:54018
41.220.114.194:41890
43.224.10.22:6666
43.243.172.2:83
43.243.172.18:83
43.243.174.3:83
43.252.10.146:2222
```

## [ARCHIVE (1823/22041)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.172:4145
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
```



Thx Co Pure Gs - Sort Meister! 💟