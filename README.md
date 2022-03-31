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

# [SAMPLE PROXIES] - [March 31 2022 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1121
   - **SOCKS5** -> 119
   - **HTTP** -> 186
   - **HTTPS** -> 152

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1578
   - **Unique Online Proxies** -> 1528
   - **Unique Online/Offline Proxies (Archive)** -> 13023

## [SOCKS4 (1121/1528)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.4.161.108:4145
1.9.164.242:35471
1.9.167.36:60489
1.10.140.43:4145
1.20.96.156:4153
1.179.130.201:4153
1.179.148.9:36476
1.179.173.114:4153
3.141.13.98:5678
4.28.96.138:39593
5.1.104.66:33041
5.58.47.25:3629
5.104.184.59:5678
5.130.72.170:5678
5.152.175.13:2580
5.153.140.179:4145
5.153.140.180:4145
5.160.39.219:3629
5.178.193.43:1080
5.178.217.227:31019
5.181.248.202:5678
5.188.64.79:5678
8.42.68.17:39593
8.42.69.93:39593
12.218.209.130:13326
13.58.223.158:5678
14.99.212.242:5678
14.102.19.50:5678
14.142.20.134:4145
14.207.27.226:5678
```

## [SOCKS5 (119/1528)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.49.222:7302
5.11.17.230:1080
14.23.50.42:7302
23.234.213.157:6666
24.249.199.4:4145
37.139.243.32:1080
39.165.98.152:7302
43.128.36.71:3389
43.129.243.128:3001
43.224.10.19:6667
43.224.10.43:6667
43.224.10.46:6667
45.142.212.31:30001
51.83.21.224:16379
51.222.13.193:10084
60.10.37.21:7302
60.12.77.43:7300
60.165.35.64:7302
60.215.109.34:7302
60.248.77.66:3000
61.7.195.206:44594
61.132.47.18:54191
61.142.70.130:7300
61.174.68.160:7300
61.174.68.160:7302
61.178.99.43:7302
61.182.207.98:7302
62.113.115.94:16072
67.210.146.50:11080
68.71.249.153:48606
```

## [HTTP (186/1528)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.13.165.87:8080
1.179.144.41:8080
2.188.166.25:3128
8.214.41.50:80
12.31.246.5:8080
14.139.184.130:3128
23.234.213.157:6666
24.113.42.177:48678
27.255.3.134:3128
31.204.180.44:53281
34.229.168.95:8118
41.164.68.42:8080
43.224.10.30:6666
43.243.172.2:82
43.243.174.3:83
45.175.160.33:999
45.181.122.73:999
45.189.118.74:999
45.235.15.15:999
46.52.180.194:8080
46.219.8.201:41890
47.115.156.64:3128
49.128.185.109:8181
49.231.200.212:8080
58.82.154.3:8080
62.75.229.51:5566
62.75.229.155:5566
62.138.7.104:5566
62.171.177.80:3128
62.205.169.74:53281
```

## [HTTPS (152/1528)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
3.20.236.208:49205
5.20.91.12:60792
18.216.72.10:49205
36.80.36.57:46210
36.89.49.55:8181
38.101.122.186:999
41.254.53.70:1976
43.129.223.147:38080
43.224.8.14:6666
45.5.119.242:999
45.81.144.51:8080
45.235.15.15:999
51.79.50.31:9300
62.75.229.155:5566
62.75.229.167:5566
62.171.177.80:3128
67.73.184.178:8081
69.63.73.171:53281
77.236.237.177:8080
77.236.248.215:1256
77.238.79.111:8080
80.90.80.54:8080
81.24.117.250:18080
82.114.118.142:1256
82.137.244.74:8080
82.202.202.2:5001
83.238.80.18:8081
84.201.254.47:3128
84.252.139.198:3128
85.25.91.155:5566
```

## [ARCHIVE (1528/13023)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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