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

# [SAMPLE PROXIES] - [October 21 2021 | 07:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 3991
   - **SOCKS5** -> 197
   - **HTTP** -> 249
   - **HTTPS** -> 370

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 4807
   - **Unique Online Proxies** -> 4643
   - **Unique Online/Offline Proxies (Archive)** -> 21754

## [SOCKS4 (3991/4643)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.1.227.187:4145
1.4.154.110:5678
1.4.214.148:5678
1.6.216.46:9999
1.9.27.214:4153
1.9.164.242:35471
1.9.213.114:4153
1.10.187.237:5678
1.14.77.107:1080
1.14.104.146:1080
1.20.95.95:5678
1.20.99.41:5678
1.20.137.82:32241
1.20.184.75:4153
1.20.227.66:4145
1.53.137.84:4145
1.55.241.4:4145
1.179.145.101:33109
1.179.147.5:52210
1.179.148.9:36476
1.179.151.165:31948
1.179.172.45:31225
1.179.181.213:30500
1.179.202.33:5678
1.186.40.2:39651
1.186.40.9:39651
1.186.40.177:39651
1.186.82.4:5678
1.186.139.9:39651
```

## [SOCKS5 (197/4643)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.14.104.146:1080
1.117.11.31:7890
3.70.188.38:1088
3.133.40.194:8080
5.34.247.41:12356
5.105.0.135:16379
5.105.1.86:16379
8.131.71.241:1080
8.210.163.246:50044
8.210.218.85:9091
8.210.251.244:24691
8.210.251.244:6655
13.250.172.147:48540
23.94.234.130:3333
27.116.51.92:6667
31.128.248.1:1080
37.52.48.238:8888
43.132.157.62:2120
43.224.8.12:6667
43.224.10.13:6667
43.224.10.42:6667
45.77.69.85:38088
46.0.234.11:5678
46.101.36.144:11475
47.104.16.8:6667
47.114.140.200:8085
47.149.68.132:1080
47.242.156.55:8080
47.242.170.47:8080
51.15.21.34:9834
```

## [HTTP (249/4643)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.15.182.239:7890
1.20.99.122:8080
1.117.100.196:7788
5.16.0.174:8080
5.56.134.237:55963
8.142.75.137:3128
8.208.91.118:8800
8.208.91.118:8080
20.206.77.128:8080
27.128.242.141:8089
34.138.225.120:8888
36.67.101.117:11111
36.91.194.25:8080
36.94.133.138:8080
36.255.86.114:83
37.75.244.8:3128
37.204.58.140:8000
37.210.194.137:8080
39.96.29.123:8080
41.77.188.178:80
41.221.158.186:31932
41.243.7.18:8080
43.135.130.68:8080
43.224.8.116:6666
43.224.10.26:6666
43.224.10.30:6666
45.65.247.67:8080
45.76.174.251:1088
45.127.56.194:83
45.162.126.1:999
```

## [HTTPS (370/4643)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.116.12.21:3228
1.117.100.196:7788
1.179.136.98:8080
2.188.166.25:3128
5.20.91.12:60792
5.56.134.237:55963
8.208.91.118:8888
14.170.154.10:8080
14.207.57.170:8080
14.241.225.167:8080
18.197.97.162:9300
20.206.77.128:8080
27.22.85.58:8100
27.128.242.141:8089
31.42.57.1:8080
31.193.120.22:8080
34.229.130.62:49205
35.187.224.178:3128
36.66.16.193:80
36.66.171.243:8080
36.66.239.125:8080
36.67.39.239:8080
36.67.52.35:8080
36.67.73.129:8080
36.91.110.195:8080
36.94.8.23:8080
36.95.69.173:8080
37.75.244.8:3128
37.139.26.54:3128
37.152.176.47:8118
```

## [ARCHIVE (4643/21754)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.145.246:4145
1.0.148.132:4145
1.0.152.157:4145
1.0.205.87:8080
1.0.239.61:5678
1.1.129.166:4145
1.1.187.210:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.227.187:4145
1.1.227.254:4145
1.1.229.44:4145
1.2.187.168:4145
1.2.252.65:8080
1.4.154.110:5678
1.4.157.35:36202
1.4.157.35:46944
1.4.183.121:4145
1.4.198.86:8081
1.4.214.148:5678
1.6.216.46:9999
1.9.27.213:4153
1.9.27.214:4153
1.9.71.4:4153
1.9.164.242:35471
1.9.165.67:4153
1.9.167.35:60489
```



Thx Co Pure Gs - Sort Meister! 💟