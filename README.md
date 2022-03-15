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

# [SAMPLE PROXIES] - [March 15 2022 | 05:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1221
   - **SOCKS5** -> 233
   - **HTTP** -> 670
   - **HTTPS** -> 640

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2764
   - **Unique Online Proxies** -> 2574
   - **Unique Online/Offline Proxies (Archive)** -> 2574

## [SOCKS4 (1221/2574)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.1.169.159:4145
1.9.27.217:4153
1.9.213.114:4153
1.10.140.43:4145
1.20.96.30:4153
1.20.184.75:4153
1.53.137.84:4145
1.186.40.177:39651
1.186.82.4:5678
1.220.145.45:4145
3.141.13.98:5678
4.28.96.138:39593
5.34.74.234:5678
5.58.53.216:1085
5.130.72.170:5678
5.153.140.179:4145
5.153.140.180:4145
5.181.248.202:5678
5.188.147.26:3629
5.189.140.8:10439
5.226.125.10:10801
8.17.28.139:39593
8.39.228.5:39593
8.39.228.33:39593
8.39.228.129:39593
8.39.228.193:39593
8.42.68.17:39593
8.42.68.93:39593
8.42.68.121:39593
8.42.69.93:39593
```

## [SOCKS5 (233/2574)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.49.222:7302
20.114.87.37:1080
23.234.213.157:6666
24.249.199.4:4145
24.249.199.12:4145
27.72.147.22:61309
31.211.131.136:33427
34.95.224.52:443
36.32.191.51:7302
36.112.209.171:7302
37.131.202.95:33427
39.104.129.141:7302
39.129.178.13:7302
39.129.178.13:7300
39.184.147.250:7302
43.129.77.148:3001
43.129.222.186:38080
43.224.10.31:6667
43.224.10.32:6667
43.224.10.35:6667
43.224.10.48:6667
45.67.229.104:30001
45.67.229.104:30003
45.76.174.194:45559
45.81.225.67:7057
45.132.236.217:8888
45.142.212.31:30002
45.142.212.31:30003
46.36.64.217:33427
46.101.5.73:45775
```

## [HTTP (670/2574)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.189.58:8080
1.10.141.220:54620
1.179.148.9:55636
1.179.232.220:8080
1.186.245.226:80
2.184.4.68:6565
2.184.4.76:6565
3.20.236.208:49205
5.16.0.174:8080
5.20.91.12:60792
5.58.58.209:8080
5.104.174.199:23500
5.160.91.130:3128
5.160.101.165:3128
5.188.136.52:8080
5.189.186.24:5566
8.208.91.118:80
12.31.246.5:8080
14.139.184.130:3128
14.207.59.105:8080
14.241.111.38:8080
18.216.72.10:49205
18.216.136.190:9090
18.222.17.49:49205
24.172.82.94:53281
27.72.95.176:8080
27.111.45.25:55443
31.3.169.45:8080
34.101.127.131:8080
36.37.177.186:8080
```

## [HTTPS (640/2574)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
1.1.189.58:8080
1.179.144.41:8080
2.184.4.70:6565
2.188.166.22:3128
3.20.236.208:49205
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.59.136.230:8080
5.180.130.90:80
5.188.136.52:8080
12.218.209.130:53281
14.102.40.97:83
14.139.184.130:3128
14.160.26.153:8080
14.161.252.185:55443
14.177.235.17:8080
14.192.2.161:84
14.192.3.161:83
14.192.3.161:82
14.241.225.134:80
14.241.225.167:80
15.235.132.138:8080
18.216.72.10:49205
18.216.136.190:9090
18.222.17.49:49205
24.43.140.138:8080
27.116.51.119:8080
27.121.85.74:8080
```

## [ARCHIVE (2574/2574)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.170.50:8080
1.1.169.159:4145
1.1.189.58:8080
1.9.27.217:4153
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.20.96.30:4153
1.20.184.75:4153
1.53.137.84:4145
1.179.144.41:8080
1.179.148.9:55636
1.179.232.220:8080
1.180.49.222:7302
1.186.40.177:39651
1.186.82.4:5678
1.186.245.226:80
1.220.145.45:4145
2.184.4.68:6565
2.184.4.70:6565
2.184.4.76:6565
2.188.166.22:3128
3.20.236.208:49205
3.141.13.98:5678
4.28.96.138:39593
5.16.0.174:8080
5.16.0.180:8080
5.20.91.12:60792
5.34.74.234:5678
5.58.53.216:1085
```



Thx Co Pure Gs - Sort Meister! 💟