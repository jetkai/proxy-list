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

# [SAMPLE PROXIES] - [March 16 2022 | 01:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 618
   - **SOCKS5** -> 201
   - **HTTP** -> 423
   - **HTTPS** -> 293

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1535
   - **Unique Online Proxies** -> 1421
   - **Unique Online/Offline Proxies (Archive)** -> 5020

## [SOCKS4 (618/1421)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.220.145.45:4145
2.183.8.145:4153
3.141.13.98:5678
5.153.140.180:4145
5.226.125.10:10801
8.42.68.121:39593
13.58.88.184:5678
13.58.223.158:5678
14.215.212.37:4153
18.216.32.60:5678
18.216.72.10:5678
24.249.199.4:4145
24.249.199.12:4145
27.131.168.137:5678
31.173.193.34:5678
35.164.231.180:35273
36.66.167.242:4153
36.71.150.135:5678
36.89.85.49:5678
36.89.149.173:4145
36.91.106.159:5678
36.91.145.5:5678
36.92.143.185:4153
36.95.84.225:5678
36.95.133.234:1080
36.95.245.81:5678
37.17.169.78:45630
37.26.136.181:39323
37.57.40.167:4145
37.98.231.12:1080
```

## [SOCKS5 (201/1421)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.11.17.230:1080
5.188.181.170:3080
24.249.199.4:4145
24.249.199.12:4145
34.95.224.52:443
36.7.79.105:7302
36.32.191.51:7302
36.112.209.171:7302
39.108.56.233:8080
39.152.104.167:7300
43.224.8.12:6667
43.251.116.58:8888
45.81.129.218:8888
45.142.212.31:30002
46.101.5.73:45775
47.97.221.159:7890
47.102.194.161:22002
47.109.40.23:1080
49.234.238.133:9999
51.38.32.239:31779
51.81.197.85:9050
51.83.21.224:16379
51.83.190.248:19050
54.37.194.101:32556
58.46.66.85:7302
58.217.115.142:7302
59.47.140.142:7302
59.59.6.86:7300
59.59.6.86:7302
59.174.31.138:7302
```

## [HTTP (423/1421)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:8080
1.1.189.58:8080
1.186.40.35:1111
1.186.85.38:1111
2.188.166.26:3128
3.20.236.208:49205
3.215.177.148:49205
5.16.7.213:1256
5.20.91.12:60792
5.58.58.209:8080
5.59.136.230:8080
5.202.115.102:8080
8.208.91.118:8008
8.214.41.50:80
12.31.246.5:8080
14.139.184.130:3128
14.207.122.162:8080
18.222.17.49:49205
24.43.140.138:8080
31.128.71.241:8081
36.66.124.193:3128
36.66.172.121:39810
36.89.49.55:8181
36.91.107.61:8080
36.92.85.66:8080
36.92.140.113:80
36.95.65.99:8019
36.95.156.127:6969
37.26.136.181:52271
37.29.80.161:8080
```

## [HTTPS (293/1421)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.186.85.38:1111
2.179.193.146:80
3.20.236.208:49205
5.20.91.12:60792
5.58.58.209:8080
5.59.136.230:8080
5.104.174.199:23500
5.189.186.24:5566
12.88.29.66:9080
12.218.209.130:53281
14.139.184.130:3128
14.241.225.134:80
14.241.225.167:80
18.216.72.10:49205
31.42.57.1:8080
34.230.89.25:49205
36.89.49.55:8181
36.92.134.71:999
38.123.78.110:999
38.123.207.249:999
38.130.248.180:999
41.216.98.122:8080
43.225.67.35:53905
43.225.67.39:53905
45.5.94.182:3128
45.121.216.219:55443
45.171.242.2:8083
45.174.249.1:999
45.177.109.220:999
45.187.21.78:34896
```

## [ARCHIVE (1421/5020)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.9.27.217:4153
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.20.96.30:4153
1.20.184.75:4153
1.32.59.217:47045
1.53.137.84:4145
1.179.130.201:4153
1.179.144.41:8080
1.179.148.9:36476
1.179.148.9:55636
1.179.173.114:4153
1.179.232.220:8080
1.180.49.222:7302
1.186.40.35:1111
1.186.40.177:39651
1.186.82.4:5678
1.186.85.38:1111
1.186.139.9:39651
1.186.213.67:5678
```



Thx Co Pure Gs - Sort Meister! 💟