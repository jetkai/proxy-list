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

# [SAMPLE PROXIES] - [October 19 2021 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 7456
   - **SOCKS5** -> 417
   - **HTTP** -> 1257
   - **HTTPS** -> 1312

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 10442
   - **Unique Online Proxies** -> 9764
   - **Unique Online/Offline Proxies (Archive)** -> 20910

## [SOCKS4 (7456/9764)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.4.154.110:5678
1.4.157.35:36202
1.4.214.148:5678
1.6.216.46:9999
1.9.27.214:4153
1.9.71.4:4153
1.9.164.242:35471
1.9.165.67:4153
1.9.167.35:60489
1.9.167.36:60489
1.10.140.43:4145
1.10.141.220:37718
1.10.187.237:5678
1.20.95.95:5678
1.20.96.164:4153
1.20.137.82:32241
1.20.168.157:4145
1.20.203.14:4145
1.20.220.79:4145
1.20.227.66:4145
1.32.57.85:5678
1.53.137.84:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.145.101:33109
1.179.147.5:52210
1.179.151.165:31948
```

## [SOCKS5 (417/9764)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.15.182.239:7890
1.116.4.222:7890
5.56.134.237:45698
5.105.0.135:16379
5.105.1.86:16379
5.164.23.101:1080
8.131.71.241:1080
8.210.163.246:50036
8.210.251.244:6666
8.210.251.244:6655
13.250.172.147:48540
14.105.19.195:1080
14.215.49.139:1080
20.52.130.140:16379
24.249.199.4:4145
24.249.199.12:4145
24.249.199.14:57335
27.76.10.118:5005
27.116.51.92:6667
27.116.51.119:6667
27.116.51.178:6667
27.116.51.181:6667
27.116.51.186:6667
31.128.248.1:1080
31.186.241.7:11277
35.171.22.27:1080
35.196.59.45:43814
35.201.142.139:10004
35.201.142.139:10002
36.27.223.80:27000
```

## [HTTP (1257/9764)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.10.141.220:54620
1.10.187.237:8080
1.20.217.221:8080
1.116.4.222:7890
2.56.240.137:8080
3.17.142.21:49205
3.90.235.224:49205
3.215.177.148:49205
5.16.0.77:1256
5.16.0.97:1256
5.58.33.187:55507
5.59.136.230:8080
5.149.219.201:8080
5.183.71.145:39305
5.202.115.102:8080
5.227.65.88:3128
5.228.203.129:8000
8.208.91.118:8000
8.208.91.118:8800
8.208.91.118:80
8.243.96.66:999
12.127.133.62:48678
12.139.210.41:8080
12.139.210.169:8080
13.58.215.184:49205
14.102.7.142:1337
14.102.152.158:8080
14.161.10.191:8080
14.177.235.17:8080
14.177.236.212:55443
```

## [HTTPS (1312/9764)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.2.252.65:8080
1.10.141.220:54620
1.10.188.78:45208
1.20.166.142:8080
1.179.183.73:50178
2.179.193.146:80
3.17.142.21:49205
3.80.224.39:49205
3.90.235.224:49205
3.215.177.148:49205
5.44.54.16:8080
5.130.90.3:8080
5.160.101.170:3128
12.139.210.41:8080
12.139.210.241:8080
12.229.217.226:55443
13.58.215.184:49205
14.160.32.23:8080
14.161.252.185:55443
14.207.57.170:8080
14.207.57.181:8080
14.241.111.38:8080
14.241.225.134:443
14.241.225.167:80
18.179.37.237:8080
18.191.253.100:49205
18.216.72.10:49205
18.234.51.98:49205
20.206.77.128:8080
```

## [ARCHIVE (9764/20910)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.9.167.36:60489
```



Thx Co Pure Gs - Sort Meister! 💟