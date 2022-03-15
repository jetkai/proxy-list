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

# [SAMPLE PROXIES] - [March 15 2022 | 09:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 535
   - **SOCKS5** -> 159
   - **HTTP** -> 298
   - **HTTPS** -> 236

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1228
   - **Unique Online Proxies** -> 1150
   - **Unique Online/Offline Proxies (Archive)** -> 4474

## [SOCKS4 (535/1150)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.20.96.30:4153
1.220.145.45:4145
2.183.8.145:4153
3.141.13.98:5678
5.130.72.170:5678
5.153.140.179:4145
5.181.248.202:5678
8.39.228.25:39593
12.7.109.227:39593
12.218.209.130:13326
13.58.88.184:5678
13.58.223.158:5678
14.63.1.108:4145
24.74.26.164:39593
24.234.142.118:31008
27.72.173.14:5678
27.123.3.140:4145
27.147.144.122:4153
27.147.144.124:4153
31.163.202.55:3629
35.164.231.180:35273
36.37.92.1:4153
36.66.16.23:5678
36.66.71.27:5678
36.67.98.158:4153
36.78.210.176:4145
36.89.17.211:5678
36.89.149.173:4145
36.89.156.211:4145
```

## [SOCKS5 (159/1150)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.49.222:7302
3.131.207.170:13343
5.11.17.230:1080
24.249.199.12:4145
27.72.147.22:61309
34.95.224.52:443
36.7.79.105:7302
36.32.191.51:7302
45.76.174.194:45559
45.142.212.31:30002
45.142.212.31:30003
47.109.40.23:1080
49.51.74.195:21127
51.38.32.239:31779
51.83.21.224:16379
51.83.190.248:19050
51.222.12.245:10084
51.222.13.193:10084
54.37.200.252:32556
54.39.87.232:39721
58.222.132.163:7302
59.47.140.142:7302
59.59.6.86:7302
59.174.31.138:7302
60.10.10.171:7302
60.12.78.34:7302
60.28.57.177:7302
61.54.227.70:7302
61.153.42.218:7302
61.163.35.38:7300
```

## [HTTP (298/1150)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.10.141.220:54620
1.179.144.41:8080
1.179.148.9:55636
5.189.186.24:5566
14.139.184.130:3128
18.216.72.10:49205
27.116.51.85:6666
36.66.103.211:3128
36.91.45.10:51672
36.91.107.61:8080
36.91.166.98:8080
36.95.27.209:8080
36.95.84.151:41890
36.95.238.195:8080
37.191.78.27:8080
41.65.67.166:1976
41.76.149.62:8080
41.191.245.37:8080
41.220.238.130:83
41.254.53.70:1976
43.224.10.36:6666
43.225.169.27:8080
43.243.174.3:83
43.245.95.178:53805
45.7.135.233:999
45.116.229.183:8080
45.161.115.80:999
45.166.144.2:999
45.175.160.49:999
45.181.205.113:8080
```

## [HTTPS (236/1150)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
1.1.189.58:8080
3.20.236.208:49205
5.20.91.12:60792
12.88.29.66:9080
18.216.72.10:49205
18.222.17.49:49205
31.128.71.241:8081
34.229.130.62:49205
34.230.89.25:49205
36.67.57.45:30066
36.89.212.250:8080
36.91.166.98:8080
36.92.70.209:8080
36.92.134.71:999
36.95.84.151:41890
37.252.73.192:8080
38.130.248.179:999
41.79.37.74:8585
41.216.98.122:8080
41.220.238.130:82
43.224.8.12:6666
43.224.10.57:6666
43.225.67.35:53905
43.225.67.39:53905
43.242.135.182:80
43.245.93.241:53805
45.172.111.5:999
45.174.249.1:999
45.227.72.50:8080
```

## [ARCHIVE (1150/4474)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.170.50:8080
1.1.169.159:4145
1.1.189.58:8080
1.2.252.65:8080
1.4.157.35:36202
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
1.179.232.220:8080
1.180.49.222:7302
1.186.40.177:39651
1.186.82.4:5678
1.186.85.38:1111
1.186.139.9:39651
1.186.245.226:80
1.220.145.45:4145
1.221.173.148:4145
2.179.193.146:80
2.183.8.145:4153
```



Thx Co Pure Gs - Sort Meister! 💟