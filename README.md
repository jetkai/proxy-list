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

# [SAMPLE PROXIES] - [April 29 2022 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1703
   - **SOCKS5** -> 227
   - **HTTP** -> 743
   - **HTTPS** -> 654

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3327
   - **Unique Online Proxies** -> 3077
   - **Unique Online/Offline Proxies (Archive)** -> 19306

## [SOCKS4 (1703/3077)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.2.212.222:4145
1.4.157.35:36202
1.4.214.148:5678
1.9.213.114:4153
1.10.140.43:4145
1.20.96.156:4153
1.32.57.85:5678
1.179.130.201:4153
1.179.147.5:52210
1.179.151.165:31948
1.179.173.114:4153
1.179.186.68:1080
1.186.85.74:5678
1.220.145.45:4145
1.221.173.148:4145
2.197.124.172:4153
3.141.13.98:5678
3.144.165.41:5555
5.34.74.234:5678
5.39.93.167:26330
5.44.254.70:4145
5.153.140.179:4145
5.160.81.157:4145
5.165.2.223:3629
5.172.188.90:5678
5.172.188.92:5678
5.178.204.235:2082
5.188.64.79:5678
5.189.229.42:1080
5.190.57.3:4153
```

## [SOCKS5 (227/3077)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.0.162:7302
5.188.181.170:3080
5.189.229.42:1080
23.234.213.157:6666
24.249.199.4:4145
24.249.199.12:4145
27.116.51.186:6667
31.128.248.2:1080
36.6.56.255:5389
36.35.240.26:7302
36.89.86.49:56845
39.106.85.163:7891
43.129.207.123:3001
43.129.243.128:3001
43.132.252.195:42311
43.154.28.50:9090
43.224.10.35:6667
43.250.172.53:8888
43.251.116.59:8888
45.10.69.98:8888
46.101.5.73:43639
46.101.227.75:1123
47.52.254.9:9100
47.240.226.173:1080
47.241.161.14:8888
49.82.27.7:8902
50.63.165.21:23859
51.75.195.157:37606
51.83.190.248:19050
51.222.13.193:10084
```

## [HTTP (743/3077)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:8080
1.1.220.100:8080
1.4.198.22:8081
1.9.155.14:8080
2.188.166.22:3128
2.188.166.25:3128
2.188.166.26:3128
3.215.177.148:49205
5.101.98.235:3128
5.104.174.199:23500
5.131.243.11:8080
5.160.101.163:3128
5.160.101.165:3128
5.160.101.170:3128
5.167.141.239:3128
5.188.136.52:8080
5.189.229.42:1081
5.202.191.226:8080
5.202.191.226:80
8.218.213.95:10809
12.31.246.5:8080
12.88.29.66:9080
14.29.139.251:8123
14.102.31.75:8080
14.162.221.252:19132
14.170.154.193:19132
14.215.212.37:9168
14.241.39.191:8080
18.216.72.10:49205
20.113.24.12:8080
```

## [HTTPS (654/3077)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
1.4.198.22:8081
1.9.155.14:8080
1.10.141.220:54620
2.188.166.22:3128
2.188.166.25:3128
2.188.166.26:3128
3.20.236.208:49205
5.180.130.91:443
5.189.229.42:1081
8.218.213.95:10809
8.242.207.164:999
12.88.29.66:9080
12.218.209.130:53281
14.170.154.193:19132
14.177.236.212:55443
27.72.105.233:19132
34.229.130.62:49205
34.230.89.25:49205
36.66.83.109:8080
36.66.108.215:8080
36.66.172.121:39810
36.89.49.55:8181
36.91.166.98:8080
36.94.58.26:4480
36.95.156.127:6969
36.95.207.233:8080
36.255.86.114:83
37.1.37.216:53281
37.26.136.181:52271
```

## [ARCHIVE (3077/19306)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.197:4145
1.0.137.61:4153
1.0.148.135:4145
1.0.149.73:4145
1.0.152.183:4145
1.0.154.38:4145
1.0.161.25:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.208.93:4145
1.0.213.104:4145
1.0.224.88:4145
1.0.232.127:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.228.123:4145
1.1.228.201:4145
1.1.244.19:4145
1.2.182.57:4145
1.2.182.121:4145
1.2.187.19:4145
1.2.187.250:4145
1.2.187.252:4145
1.2.202.204:3629
```



Thx Co Pure Gs - Sort Meister! 💟