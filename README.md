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

# [SAMPLE PROXIES] - [April 22 2022 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 953
   - **SOCKS5** -> 174
   - **HTTP** -> 302
   - **HTTPS** -> 237

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1666
   - **Unique Online Proxies** -> 1561
   - **Unique Online/Offline Proxies (Archive)** -> 17860

## [SOCKS4 (953/1561)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.2.182.121:4145
1.2.215.190:4145
1.10.133.179:4145
1.20.95.95:5678
1.32.57.85:5678
1.179.151.165:31948
1.179.186.69:1080
1.186.40.9:39651
1.186.46.36:5678
2.50.153.41:4145
2.57.8.76:4153
4.28.96.166:39593
5.1.104.66:33041
5.34.74.234:5678
5.35.64.229:9999
5.39.93.167:49698
5.189.229.42:1080
5.190.57.3:4153
8.39.228.170:39593
8.40.133.10:1099
8.42.68.125:39593
8.44.216.242:62345
12.158.87.26:39593
12.228.137.37:32307
13.58.223.158:5678
14.63.1.108:4145
14.102.43.58:9999
14.102.101.254:4153
14.160.3.77:5678
```

## [SOCKS5 (174/1561)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.71.170.146:7302
5.39.93.167:49698
5.188.181.170:3080
5.189.229.42:1080
8.44.216.242:62345
8.210.156.241:1080
8.210.193.245:1080
8.218.26.66:1080
18.206.250.157:20000
18.213.116.166:20000
24.249.199.4:4145
24.249.199.12:4145
27.116.51.119:6667
31.128.248.1:1080
37.187.73.136:28707
43.128.7.195:1080
43.129.77.148:3001
43.129.207.123:3001
43.224.10.8:6667
43.224.10.42:6667
43.224.10.43:6667
43.224.10.57:6667
43.249.11.61:8888
45.55.43.136:22544
46.101.5.73:45775
46.146.245.5:1080
47.75.104.56:26126
47.242.111.65:1080
47.242.240.95:1080
47.243.56.254:1080
```

## [HTTP (302/1561)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.4.198.22:8081
1.179.136.98:8080
2.184.4.68:6565
5.22.196.30:8080
5.131.243.252:8080
14.102.13.161:8080
14.228.186.244:19132
31.161.38.233:8090
36.66.172.121:39810
36.67.52.35:8080
37.1.37.216:53281
37.59.50.50:8118
37.187.146.176:8118
41.33.86.242:8080
41.59.200.20:9999
41.77.13.186:53281
43.225.67.35:53905
43.243.172.2:82
43.243.172.18:83
43.245.93.241:53805
43.249.224.172:84
43.250.126.1:9001
45.5.58.34:999
45.5.68.18:999
45.5.68.33:999
45.7.132.194:999
45.160.78.53:999
45.164.150.122:999
45.169.148.2:999
45.170.101.177:999
```

## [HTTPS (237/1561)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:8080
14.241.39.165:19132
18.222.17.49:49205
27.72.105.233:19132
31.161.38.233:8090
36.91.68.148:8080
36.95.65.99:8019
37.204.157.91:41890
40.136.41.6:8080
41.86.251.61:8080
41.216.98.122:8080
43.249.224.170:83
43.250.127.98:9001
43.252.10.146:2222
43.252.10.212:2222
45.65.132.148:8080
45.71.203.100:999
45.71.203.104:999
45.122.233.76:55443
45.189.113.15:999
45.189.117.237:999
45.189.254.49:999
45.190.79.160:999
45.250.226.14:8080
46.99.205.10:8080
46.209.196.147:8080
46.243.220.101:8118
49.51.138.111:8118
50.192.250.60:8080
50.250.56.129:46456
```

## [ARCHIVE (1561/17860)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.168:4145
1.0.136.197:4145
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
1.2.182.121:4145
1.2.187.19:4145
1.2.187.250:4145
1.2.187.252:4145
1.2.202.204:3629
1.2.205.171:8080
1.2.215.190:4145
1.2.222.252:4145
```



Thx Co Pure Gs - Sort Meister! 💟