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

# [SAMPLE PROXIES] - [November 01 2021 | 11:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2480
   - **SOCKS5** -> 180
   - **HTTP** -> 474
   - **HTTPS** -> 497

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3631
   - **Unique Online Proxies** -> 3468
   - **Unique Online/Offline Proxies (Archive)** -> 26309

## [SOCKS4 (2480/3468)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.1.227.53:4145
1.4.195.114:4145
1.9.27.214:4153
1.9.71.4:4153
1.9.164.242:35471
1.10.165.200:4145
1.20.137.82:32241
1.20.198.8:4153
1.20.198.10:4153
1.179.148.9:36476
1.179.151.165:31948
1.186.40.9:39651
1.186.40.157:39651
1.186.82.4:5678
2.62.136.144:1080
2.139.162.80:4145
2.186.231.165:5678
3.141.13.98:5678
3.144.250.151:1080
5.1.104.66:33041
5.42.124.221:1099
5.56.133.204:4444
5.105.1.86:16379
5.130.72.170:5678
5.141.81.106:44271
5.149.218.10:5678
5.153.140.180:4145
5.160.39.226:5678
5.160.72.148:43130
5.167.171.15:3629
```

## [SOCKS5 (180/3468)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.56.134.237:45698
5.105.1.86:16379
8.210.179.3:25170
13.250.172.147:48540
14.192.9.155:1080
14.192.10.24:1080
20.198.168.89:1080
23.94.200.180:1080
23.94.234.130:3333
31.128.248.2:1080
34.101.205.13:1080
36.94.126.50:1080
37.187.72.30:57257
39.108.174.232:9999
43.135.28.99:1088
43.135.95.75:1080
43.224.10.26:6667
43.224.10.30:6667
43.224.10.43:6667
45.77.61.119:38088
45.119.82.17:37730
46.0.234.11:5678
46.101.36.144:11475
47.106.218.216:1080
47.149.68.132:1080
47.242.52.110:1080
47.243.190.108:7891
51.15.242.51:1080
51.79.166.152:10084
58.32.42.8:1080
```

## [HTTP (474/3468)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.99.122:8080
3.215.177.148:49205
5.16.0.174:8080
5.44.54.16:8080
5.56.134.237:55963
5.164.211.117:8080
5.183.234.1:8080
5.190.29.161:8080
14.161.10.191:8080
27.42.168.46:55481
27.147.193.82:8080
31.47.37.92:8080
34.101.248.243:3128
34.138.225.120:8888
34.141.35.135:3128
36.67.27.189:39674
36.67.152.213:11111
36.73.159.10:8080
36.78.223.118:8080
36.89.190.85:8080
36.90.61.82:8080
36.91.107.61:8080
36.91.133.49:10000
36.92.116.26:8080
36.94.47.58:4480
36.94.61.196:4480
36.94.224.201:8080
36.95.54.114:8080
36.95.207.233:8080
37.75.244.8:3128
```

## [HTTPS (497/3468)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.1.189.58:8080
1.10.141.220:54620
1.179.148.9:55636
2.179.193.146:80
3.94.93.17:49205
5.130.90.3:8080
5.133.27.61:3129
5.141.82.95:81
14.207.79.42:8080
14.207.147.157:8080
14.207.179.34:8080
18.191.253.100:49205
18.234.51.98:49205
27.72.95.176:8080
27.72.149.205:8080
27.105.130.93:8080
31.47.37.92:8080
34.101.248.243:3128
34.141.35.135:3128
36.66.172.121:39810
36.67.27.189:39674
36.67.168.123:8080
36.92.70.209:8080
36.92.116.26:8080
36.92.189.66:80
36.92.189.66:8080
36.94.13.63:3128
36.94.79.241:8080
36.94.224.201:8080
36.95.69.173:8080
```

## [ARCHIVE (3468/26309)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.145.246:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.163.172:8081
1.0.205.87:8080
1.0.213.133:8080
1.0.239.61:5678
1.1.128.155:5678
1.1.129.166:4145
1.1.167.139:4145
1.1.187.210:4145
1.1.189.58:8080
1.1.214.117:8081
1.1.220.100:8080
1.1.227.53:4145
1.1.227.187:4145
1.1.227.254:4145
1.1.229.44:4145
1.1.240.121:5678
1.2.187.41:4145
1.2.187.111:4145
1.2.187.168:4145
1.2.200.79:8080
1.2.214.154:4145
1.2.252.65:8080
1.4.154.110:5678
1.4.157.35:36202
```



Thx Co Pure Gs - Sort Meister! 💟