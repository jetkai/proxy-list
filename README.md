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

# [SAMPLE PROXIES] - [April 16 2022 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 963
   - **SOCKS5** -> 183
   - **HTTP** -> 672
   - **HTTPS** -> 552

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2370
   - **Unique Online Proxies** -> 2193
   - **Unique Online/Offline Proxies (Archive)** -> 16961

## [SOCKS4 (963/2193)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.9.27.217:4153
1.9.167.35:60489
1.9.167.36:60489
1.10.189.133:50855
1.20.96.30:4153
1.53.137.84:4145
1.83.154.28:4145
1.179.147.5:52210
1.179.151.165:31948
1.179.186.68:1080
1.186.46.36:5678
3.141.13.98:5678
4.14.120.234:39593
5.1.104.66:33041
5.22.154.50:32127
5.58.47.25:3629
5.58.53.216:1085
5.153.140.179:4145
5.165.2.223:3629
5.180.100.24:5678
5.188.64.79:5678
8.39.228.161:39593
12.11.59.114:1080
12.187.55.1:39593
12.216.103.114:39072
13.58.88.184:5678
13.58.223.158:5678
14.63.1.108:4145
14.102.44.1:34047
14.224.172.179:5678
```

## [SOCKS5 (183/2193)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.196.182.180:1080
5.11.17.230:1080
5.39.93.167:20352
5.157.80.66:1080
5.189.229.42:1080
8.218.9.170:1080
24.249.199.4:4145
24.249.199.12:4145
27.191.191.27:7302
37.131.202.95:33427
43.128.36.71:3389
43.129.77.148:3001
43.129.207.123:3001
45.55.32.201:62991
45.55.32.201:41253
45.76.188.101:21955
45.90.57.69:40021
46.101.5.73:45199
46.101.5.73:45775
47.240.226.173:1080
49.51.69.212:21127
49.51.186.129:21127
51.68.37.227:13767
51.68.37.227:29595
51.68.37.227:16047
51.77.73.70:1080
51.77.141.29:1080
51.79.52.80:3080
51.155.3.184:33427
51.195.151.189:9320
```

## [HTTP (672/2193)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.1.220.100:8080
1.162.40.85:8080
1.174.183.162:8080
1.186.85.38:1111
5.16.0.174:8080
5.16.0.180:8080
5.149.219.201:8080
5.180.130.90:8080
5.180.130.90:443
5.188.136.52:8080
5.189.186.24:5566
5.189.229.42:1081
8.213.128.19:80
8.213.128.30:80
8.213.128.78:80
8.213.128.106:80
8.213.128.114:80
8.213.128.123:80
8.213.128.127:80
8.213.128.131:80
8.213.128.149:80
8.213.128.152:80
8.213.128.171:80
8.213.128.172:80
8.213.128.202:80
8.213.128.214:80
8.213.128.253:80
8.213.129.23:80
8.213.129.34:80
8.213.129.36:80
```

## [HTTPS (552/2193)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
1.0.205.87:8080
1.20.217.52:8080
1.186.85.38:1111
1.186.245.226:1111
2.179.193.146:80
5.16.0.174:8080
5.160.91.130:3128
5.189.229.42:1081
8.213.128.30:80
8.218.213.95:10809
8.242.207.164:999
12.218.209.130:53281
14.102.40.97:83
14.161.252.185:55443
14.241.111.38:8080
27.22.85.52:8100
27.72.244.228:8080
27.116.51.181:6666
31.42.57.1:8080
31.204.180.44:53281
31.220.183.217:53281
34.229.130.62:49205
34.230.89.25:49205
36.66.19.10:8080
36.66.124.193:3128
36.67.52.35:8080
36.67.237.146:3128
36.80.36.57:46210
36.92.93.61:8080
```

## [ARCHIVE (2193/16961)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.137.61:4153
1.0.149.73:4145
1.0.152.183:4145
1.0.154.38:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.0.208.93:4145
1.0.213.104:4145
1.0.224.88:4145
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.1.228.123:4145
1.1.228.201:4145
1.1.244.19:4145
1.2.182.57:4145
1.2.187.19:4145
1.2.187.250:4145
1.2.187.252:4145
1.2.202.204:3629
1.2.205.171:8080
1.2.215.190:4145
1.2.222.252:4145
1.2.252.65:8080
1.4.157.35:36202
```



Thx Co Pure Gs - Sort Meister! 💟