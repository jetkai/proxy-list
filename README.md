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

# [SAMPLE PROXIES] - [March 20 2022 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 778
   - **SOCKS5** -> 105
   - **HTTP** -> 567
   - **HTTPS** -> 349

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 1799
   - **Unique Online Proxies** -> 1714
   - **Unique Online/Offline Proxies (Archive)** -> 10891

## [SOCKS4 (778/1714)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.10.189.133:50855
1.20.104.159:4145
1.20.184.75:4153
1.55.241.4:4145
1.179.145.101:33109
1.186.40.177:39651
3.141.13.98:5678
4.28.96.138:39593
4.28.96.254:39593
5.22.154.50:32127
5.133.24.167:5678
5.152.86.46:14888
5.165.2.223:3629
5.181.171.134:1085
5.190.60.221:3629
5.226.125.10:10801
8.40.133.10:1099
8.42.68.17:39593
8.42.68.42:39593
8.42.68.49:39593
8.42.68.93:39593
8.42.68.125:39593
8.42.68.197:39593
8.42.71.226:39593
12.216.103.114:39072
12.228.137.37:32307
13.58.88.184:5678
13.58.223.158:5678
14.63.1.108:4145
14.241.229.155:51080
```

## [SOCKS5 (105/1714)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.131.207.170:13343
8.210.48.101:17681
23.234.213.157:6666
31.128.248.1:1080
34.95.224.52:443
36.32.191.51:7302
39.108.56.233:8080
39.152.104.167:7302
43.128.36.71:3389
43.224.10.33:6667
45.63.48.64:11889
45.142.212.31:30001
45.142.214.123:30001
47.245.56.108:18181
51.83.190.248:19050
51.155.3.184:33427
54.38.110.231:48325
58.18.36.61:7302
60.12.72.206:7300
60.215.109.34:7302
61.132.47.18:54191
61.153.42.218:7302
61.191.149.44:7302
62.113.115.94:16072
69.163.163.216:54366
78.136.243.21:33427
79.137.34.146:42884
84.238.219.216:33427
89.108.81.117:1080
89.201.4.136:33427
```

## [HTTP (567/1714)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.13.165.87:8080
1.186.245.226:80
2.188.166.22:3128
2.188.166.26:3128
5.16.0.77:1256
5.16.0.174:8080
5.16.1.17:8080
5.160.91.130:3128
5.189.186.24:5566
8.208.91.118:8800
8.214.41.50:80
14.187.207.53:19132
14.207.16.135:8080
14.215.212.37:9168
18.222.17.49:49205
27.72.105.233:19132
27.121.85.74:8080
27.255.3.134:3128
31.10.2.149:8080
31.42.57.1:8080
36.37.81.135:8080
36.67.52.35:8080
36.91.107.61:8080
36.91.133.49:10000
36.92.43.107:8080
36.92.85.66:8080
36.92.165.91:8080
36.94.17.138:8080
36.94.161.219:8080
36.94.199.131:8080
```

## [HTTPS (349/1714)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.32.59.217:47045
5.16.0.49:8080
5.20.91.12:60792
5.58.33.187:55507
14.139.184.130:3128
14.170.154.10:8080
14.177.235.17:8080
18.222.17.49:49205
27.116.51.186:6666
27.147.209.215:8080
34.229.130.62:49205
34.230.89.25:49205
36.91.45.10:51672
36.94.17.138:8080
36.95.15.147:8080
36.95.79.7:41890
38.101.122.186:999
41.33.86.242:8080
41.57.37.12:8080
41.254.53.70:1981
43.225.67.35:53905
43.225.67.39:53905
43.243.174.3:82
45.5.119.242:999
45.6.4.58:8080
45.43.63.230:10001
45.70.15.3:8080
45.70.201.178:999
45.187.21.78:34896
```

## [ARCHIVE (1714/10891)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.0.154.38:4145
1.0.170.50:8080
1.0.170.50:80
1.0.205.87:8080
1.1.169.159:4145
1.1.189.58:8080
1.1.220.100:8080
1.2.182.57:4145
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
1.10.140.43:4145
1.10.141.220:37718
1.10.141.220:54620
1.10.189.133:50855
1.13.165.87:8080
1.20.95.95:5678
1.20.96.30:4153
1.20.96.156:4153
```



Thx Co Pure Gs - Sort Meister! 💟