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

# [SAMPLE PROXIES] - [March 30 2022 | 07:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 593
   - **SOCKS5** -> 88
   - **HTTP** -> 212
   - **HTTPS** -> 152

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1045
   - **Unique Online Proxies** -> 1000
   - **Unique Online/Offline Proxies (Archive)** -> 12850

## [SOCKS4 (593/1000)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.20.227.66:4145
3.141.13.98:5678
4.14.120.230:39593
4.28.96.166:39593
5.34.74.234:5678
5.58.47.25:3629
5.101.65.78:6624
5.178.193.43:1080
5.180.100.24:5678
5.226.125.10:10801
8.39.228.170:39593
13.58.88.184:5678
13.58.223.158:5678
14.102.19.50:5678
14.102.44.25:34047
14.102.78.67:4145
14.207.73.121:14153
14.232.163.52:10801
14.241.182.44:5678
18.216.32.60:5678
18.216.72.10:5678
24.249.199.4:4145
27.42.168.46:61308
27.116.51.181:6667
27.116.51.186:6667
27.147.241.134:10800
31.179.162.78:4153
31.209.98.18:51688
36.37.94.199:5678
36.66.16.23:5678
```

## [SOCKS5 (88/1000)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.11.17.230:1080
24.249.199.4:4145
31.211.131.136:33427
39.152.104.167:7302
43.128.36.71:3389
43.129.77.148:3001
43.135.74.226:38081
43.224.10.26:6667
43.224.10.30:6667
46.101.5.73:48528
51.222.13.193:10084
54.39.87.232:39721
58.18.36.61:7302
58.21.199.78:7302
58.46.66.85:7302
60.248.77.66:3000
61.132.47.18:54191
61.175.220.11:7302
61.178.172.95:7300
61.178.172.95:7302
62.113.115.94:16072
67.201.33.10:25283
72.195.34.42:4145
72.195.34.59:4145
72.195.114.169:4145
72.206.181.123:4145
72.210.252.137:4145
72.217.216.239:4145
72.221.172.203:4145
72.221.232.155:4145
```

## [HTTP (212/1000)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.13.165.87:8080
2.179.193.146:80
5.61.47.22:3128
5.149.219.201:8080
5.189.186.24:5566
36.89.49.55:8181
36.92.43.107:8080
36.95.34.106:8080
37.26.136.181:52271
37.139.26.54:3128
37.191.78.27:8080
38.7.16.61:999
38.123.207.249:999
40.136.41.6:8080
41.86.251.61:8080
43.224.10.13:6666
43.225.67.39:53905
43.228.95.122:82
45.32.83.231:3128
45.133.245.159:3128
45.177.109.197:8080
45.224.153.39:999
45.236.120.93:999
46.0.203.186:8080
46.18.202.204:8080
46.219.8.201:41890
49.156.42.210:8080
51.68.199.120:3128
51.250.17.27:8080
52.91.171.186:49205
```

## [HTTPS (152/1000)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.32.59.217:47045
5.56.133.132:3128
5.189.186.24:5566
8.214.41.50:80
12.88.29.66:9080
14.207.125.75:8080
14.241.225.134:80
23.234.213.157:6666
36.91.166.98:8080
36.92.93.61:8080
36.92.134.71:999
36.95.238.195:8080
37.26.86.206:47464
39.108.56.233:8080
43.129.223.147:38080
45.5.57.122:8080
45.6.103.144:8080
45.6.103.151:8080
45.118.166.114:8080
45.160.74.1:999
45.174.87.18:999
45.189.112.225:999
45.224.153.39:999
45.235.15.15:999
46.173.214.14:8118
49.51.138.111:8118
58.97.72.83:8080
61.7.141.30:8080
62.75.229.167:5566
62.75.236.132:5566
```

## [ARCHIVE (1000/12850)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.10.141.220:54620
```



Thx Co Pure Gs - Sort Meister! 💟