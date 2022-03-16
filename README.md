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

# [SAMPLE PROXIES] - [March 16 2022 | 07:29:02]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 643
   - **SOCKS5** -> 204
   - **HTTP** -> 325
   - **HTTPS** -> 244

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1416
   - **Unique Online Proxies** -> 1335
   - **Unique Online/Offline Proxies (Archive)** -> 5878

## [SOCKS4 (643/1335)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.4.157.35:36202
1.55.241.4:4145
1.179.130.201:4153
1.212.157.115:4145
2.183.8.145:4153
3.141.13.98:5678
5.22.154.50:32127
5.58.47.25:3629
5.152.86.46:14888
5.172.188.93:5678
5.188.211.54:7777
13.58.88.184:5678
13.58.223.158:5678
14.102.19.50:5678
14.248.80.34:5678
18.188.253.82:5555
18.216.32.60:5678
18.216.72.10:5678
24.234.142.122:31008
24.249.199.4:4145
27.72.147.22:61309
27.123.1.34:4153
27.147.131.219:50391
27.147.144.122:4153
27.147.149.36:5678
31.206.38.55:37630
31.220.5.132:41080
35.164.231.180:35273
36.37.94.199:5678
```

## [SOCKS5 (204/1335)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.11.17.230:1080
5.188.181.170:3080
14.23.50.42:7302
23.234.213.157:6666
24.249.199.4:4145
24.249.199.12:4145
27.72.147.22:61309
34.95.224.52:443
36.7.79.105:7302
36.112.209.171:7302
39.152.104.167:7300
39.152.104.167:7302
39.184.147.250:7302
43.224.8.116:6667
45.55.32.201:1540
45.55.32.201:12289
45.142.212.31:30002
46.101.5.73:47521
46.101.5.73:45775
47.109.40.23:1080
47.242.168.35:9090
50.63.165.21:23859
51.79.52.80:3080
51.83.21.224:16379
51.83.190.248:19050
51.222.13.193:10084
54.37.90.13:40032
54.37.200.252:29244
58.21.199.78:7302
58.217.115.142:7302
```

## [HTTP (325/1335)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.179.144.41:8080
1.186.245.226:80
2.179.193.146:80
3.20.236.208:49205
5.16.7.213:1256
5.34.153.142:8080
14.139.184.130:3128
14.161.252.185:55443
14.207.122.162:8080
14.241.111.38:8080
18.216.72.10:49205
24.113.42.177:48678
31.204.180.44:53281
36.66.172.121:39810
36.67.27.189:39674
36.89.49.55:8181
36.89.252.155:8080
36.91.98.115:8181
36.91.107.61:8080
36.92.85.66:8080
36.94.199.131:8080
36.95.238.195:8080
36.95.249.157:8080
37.26.136.181:52271
37.57.38.133:44299
37.191.78.27:8080
38.10.246.84:999
39.108.56.233:8090
41.220.238.130:83
43.241.29.201:8080
```

## [HTTPS (244/1335)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.32.59.217:47045
3.20.236.208:49205
5.34.153.142:8080
8.214.41.50:80
14.160.29.90:8080
18.216.72.10:49205
18.222.17.49:49205
34.229.130.62:49205
34.230.89.25:49205
36.89.212.250:8080
36.89.212.254:8080
36.91.107.61:8080
36.92.70.209:8080
36.94.183.153:8080
36.94.199.131:8080
36.95.15.147:8080
36.95.84.151:41890
37.139.26.54:3128
38.10.246.84:999
41.65.67.166:1981
41.65.162.75:1976
41.111.204.186:8080
41.203.83.66:8080
43.224.8.14:6666
43.224.10.46:6666
43.225.67.39:53905
45.6.4.58:8080
45.71.200.65:999
45.167.95.184:8085
45.172.111.2:999
```

## [ARCHIVE (1335/5878)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.170.50:8080
1.1.169.159:4145
1.1.189.58:8080
1.2.187.252:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.195.114:4145
1.4.214.148:5678
1.9.27.217:4153
1.9.167.35:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.20.96.30:4153
1.20.184.75:4153
1.32.59.217:47045
1.53.137.84:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.144.41:8080
1.179.147.5:52210
1.179.148.9:36476
1.179.148.9:55636
1.179.173.114:4153
1.179.186.71:1080
1.179.232.220:8080
1.180.49.222:7302
1.186.40.35:1111
```



Thx Co Pure Gs - Sort Meister! 💟