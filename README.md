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

# [SAMPLE PROXIES] - [May 29 2022 | 04:42:30]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 603
   - **SOCKS5** -> 129
   - **HTTP** -> 128
   - **HTTPS** -> 117

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 815
   - **Unique Online Proxies** -> 815
   - **Unique Online/Offline Proxies (Archive)** -> 815

## [SOCKS4 (603/815)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.89:4153
1.20.96.30:4153
1.20.220.79:4145
3.120.173.144:8080
3.141.13.98:5678
3.211.17.212:80
5.8.240.91:4153
5.34.74.234:5678
5.44.254.40:4145
5.178.204.235:2082
5.180.100.24:5678
8.17.28.139:39593
8.42.68.197:39593
8.218.69.97:8000
12.151.56.30:80
12.187.55.1:39593
13.58.88.184:5678
13.58.223.158:5678
14.102.64.209:60616
14.215.212.37:4153
14.241.170.106:5678
14.241.225.179:5678
18.206.33.119:8888
18.216.32.60:5678
18.216.72.10:5678
23.31.119.146:1080
24.88.66.70:64312
27.123.4.238:5678
31.43.63.70:4145
31.173.251.198:40547
```

## [SOCKS5 (129/815)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.120.173.144:8080
3.131.207.170:13343
3.211.17.212:80
5.161.86.206:1080
5.161.100.145:1080
5.189.186.24:5566
5.253.145.247:1080
8.218.69.97:8000
12.151.56.30:80
18.206.33.119:8888
27.128.196.205:7302
35.244.6.175:1080
36.7.108.56:9091
36.35.240.26:7302
39.175.75.8:30001
43.128.7.195:1080
43.129.207.123:3001
43.132.203.188:57890
43.224.10.30:6667
47.74.226.8:5001
47.89.153.213:80
47.240.226.173:1080
49.12.156.165:80
49.51.189.171:21127
51.15.8.75:3738
51.155.3.184:33427
58.20.184.187:9091
58.20.232.245:9091
58.20.235.180:9091
60.215.109.34:7302
```

## [HTTP (128/815)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
3.20.236.208:49205
3.215.177.148:49205
5.104.174.199:23500
18.216.72.10:5678
18.222.17.49:49205
20.203.120.85:80
36.66.172.121:39810
36.93.2.50:8080
43.154.71.147:8118
43.224.10.30:6667
43.254.132.123:8118
45.153.165.118:999
45.167.125.209:9992
45.190.249.100:8080
45.191.196.254:999
46.209.131.246:8080
49.12.156.165:80
51.15.8.75:3738
51.195.211.154:8080
52.91.171.186:49205
58.27.255.98:8080
76.186.82.159:8118
80.91.125.119:8089
81.95.45.234:8080
81.174.11.159:43516
82.150.177.19:8080
85.133.130.18:8080
89.250.152.76:8080
91.242.213.247:8080
92.249.122.108:58749
```

## [HTTPS (117/815)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
3.20.236.208:49205
3.215.177.148:49205
5.104.174.199:23500
5.135.176.161:10000
14.177.235.17:8080
18.216.72.10:5678
18.222.17.49:49205
34.229.130.62:49205
34.230.89.25:49205
36.66.172.121:39810
36.67.152.213:11111
36.93.2.50:8080
41.242.116.235:50000
42.192.22.233:8118
43.224.10.30:6667
43.254.132.123:8118
45.153.165.118:999
45.190.249.100:8080
46.209.131.246:8080
52.91.171.186:49205
58.27.255.98:8080
61.7.159.133:8081
80.90.80.54:8080
80.91.125.119:8089
81.174.11.159:43516
85.31.251.62:8080
88.255.185.230:8080
94.101.140.131:9999
94.231.178.249:9797
95.216.194.46:1080
```

## [ARCHIVE (815/815)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.133.89:4153
1.20.96.30:4153
1.20.220.79:4145
3.20.236.208:49205
3.120.173.144:8080
3.131.207.170:13343
3.141.13.98:5678
3.211.17.212:80
3.215.177.148:49205
5.8.240.91:4153
5.34.74.234:5678
5.44.254.40:4145
5.104.174.199:23500
5.135.176.161:10000
5.161.86.206:1080
5.161.100.145:1080
5.178.204.235:2082
5.180.100.24:5678
5.189.186.24:5566
5.253.145.247:1080
8.17.28.139:39593
8.42.68.197:39593
8.218.69.97:8000
12.151.56.30:80
12.187.55.1:39593
13.58.88.184:5678
13.58.223.158:5678
14.102.64.209:60616
14.177.235.17:8080
14.215.212.37:4153
```



Thx Co Pure Gs - Sort Meister! 💟