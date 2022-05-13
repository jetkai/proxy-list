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

# [SAMPLE PROXIES] - [May 13 2022 | 01:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1455
   - **SOCKS5** -> 153
   - **HTTP** -> 472
   - **HTTPS** -> 478

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2558
   - **Unique Online Proxies** -> 2448
   - **Unique Online/Offline Proxies (Archive)** -> 20864

## [SOCKS4 (1455/2448)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.10.133.62:4145
1.53.137.84:4145
1.179.147.5:52210
1.186.40.9:39651
1.186.139.9:39651
1.220.145.45:4145
2.135.223.134:5678
2.197.124.172:4153
3.141.13.98:5678
5.8.240.94:4153
5.22.154.50:32127
5.58.47.25:3629
5.58.53.216:1085
5.135.24.186:808
5.172.188.92:5678
5.172.188.93:5678
5.178.217.227:31019
5.190.57.3:4153
5.190.60.221:3629
5.190.124.227:5678
8.39.228.5:39593
8.39.228.161:39593
8.40.133.10:1099
8.42.68.197:39593
8.42.71.226:39593
12.158.87.26:39593
12.218.209.130:13326
13.58.88.184:5678
13.58.223.158:5678
```

## [SOCKS5 (153/2448)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.13.165.87:33080
1.13.165.87:8080
5.9.2.236:1080
5.44.41.80:61400
5.253.145.247:1080
13.233.84.6:39998
14.23.62.59:7300
27.116.51.119:6667
31.25.92.5:44949
31.43.203.100:1080
31.184.220.67:1080
35.221.141.118:1080
36.35.240.26:7302
37.131.202.95:33427
37.192.253.250:1080
42.192.198.63:7891
43.128.7.195:1080
43.129.207.123:3001
43.129.243.128:3001
43.224.10.31:6667
43.224.10.32:6667
45.77.168.25:1080
45.90.57.69:40021
46.101.5.73:47521
46.101.5.73:48528
46.101.5.73:45199
46.101.5.73:45775
46.101.5.73:48334
47.115.142.217:9999
47.240.226.173:1080
```

## [HTTP (472/2448)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.13.165.87:8080
1.186.85.2:1111
3.20.236.208:49205
5.58.58.209:8080
5.61.38.247:3128
5.131.243.10:8080
8.208.91.118:81
8.242.207.202:8080
12.90.37.182:8181
12.144.254.185:9080
12.220.14.50:8181
14.20.235.19:45770
14.102.13.161:8080
14.160.29.90:8080
14.177.235.17:8080
18.216.72.10:49205
20.113.24.12:8080
24.106.221.230:53281
24.172.82.94:53281
27.111.45.25:55443
27.116.51.119:8080
31.43.52.176:41890
31.131.67.14:8080
36.66.108.215:8080
36.91.68.147:8080
36.91.148.37:8080
36.92.85.66:8080
36.92.140.113:80
36.93.35.153:9812
36.94.54.93:8080
```

## [HTTPS (478/2448)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.13.165.87:33080
1.32.59.217:47045
1.186.245.226:1111
3.20.236.208:49205
5.56.133.132:3128
5.160.91.130:3128
5.202.191.226:8080
14.20.235.19:45770
14.170.154.193:19132
14.248.80.77:8080
18.216.72.10:49205
18.222.17.49:49205
20.113.24.12:8080
27.72.105.233:19132
27.116.51.119:6666
31.128.71.241:8081
34.229.130.62:49205
34.230.89.25:49205
36.67.150.247:8080
36.91.68.148:8080
36.92.93.61:8080
36.92.134.71:999
36.93.6.170:8080
36.94.8.23:8080
36.94.40.123:9812
36.94.58.26:4480
36.94.58.28:4480
36.94.183.153:8080
36.94.199.131:8080
36.95.53.227:8080
```

## [ARCHIVE (2448/20864)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.0.161.232:4145
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
1.2.176.179:8080
1.2.180.111:4145
1.2.182.57:4145
1.2.182.121:4145
1.2.187.19:4145
```



Thx Co Pure Gs - Sort Meister! 💟