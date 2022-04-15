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

# [SAMPLE PROXIES] - [April 15 2022 | 05:29:04]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 1235
   - **SOCKS5** -> 213
   - **HTTP** -> 729
   - **HTTPS** -> 539

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 2716
   - **Unique Online Proxies** -> 2512
   - **Unique Online/Offline Proxies (Archive)** -> 16818

## [SOCKS4 (1235/2512)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.136.168:4145
1.20.96.30:4153
1.32.57.85:5678
1.83.154.28:4145
1.179.186.71:1080
2.50.153.41:4145
2.57.8.76:4153
3.141.13.98:5678
4.28.96.138:39593
4.28.96.169:39593
5.32.181.188:56002
5.35.64.229:9999
5.44.254.70:4145
5.83.93.133:4153
5.104.184.59:5678
5.130.72.170:5678
5.135.24.186:808
5.172.188.92:5678
5.178.193.43:1080
5.178.204.235:2082
5.181.248.202:5678
5.189.229.42:1080
5.194.177.146:5678
8.39.228.33:39593
8.39.228.170:39593
8.42.68.126:39593
8.42.68.197:39593
8.42.71.1:39593
8.42.71.226:39593
```

## [SOCKS5 (213/2512)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
5.11.17.230:1080
5.35.64.229:9999
5.188.181.170:3080
5.189.229.42:1080
8.210.118.170:1080
8.210.156.241:1080
8.210.193.245:1080
8.218.8.25:1080
13.233.84.6:9999
14.149.69.217:7300
20.88.238.3:1080
20.239.51.24:8080
24.249.199.4:4145
24.249.199.12:4145
27.72.104.138:51203
31.43.203.100:1080
31.128.248.2:1080
43.128.7.195:1080
43.129.207.123:3001
43.129.243.128:3001
43.135.74.226:38081
43.224.10.43:6667
43.250.172.53:8888
45.55.32.201:41253
45.76.188.101:15648
46.101.5.73:48528
47.240.226.173:1080
47.242.240.95:1080
47.243.206.239:1080
47.243.249.111:1080
```

## [HTTP (729/2512)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.179.144.41:8080
2.179.193.146:80
5.16.0.18:8080
5.16.0.77:1256
5.16.0.97:1256
5.16.0.174:8080
5.16.1.17:8080
5.149.219.201:8080
5.189.186.24:5566
5.189.229.42:1081
8.213.128.19:80
8.213.128.30:80
8.213.128.78:80
8.213.128.106:80
8.213.128.114:80
8.213.128.127:80
8.213.128.149:80
8.213.128.152:80
8.213.128.158:80
8.213.128.172:80
8.213.128.214:80
8.213.128.253:80
8.213.129.34:80
8.213.129.36:80
8.213.129.51:80
8.213.129.196:80
8.213.129.243:80
14.102.13.193:8080
14.102.47.206:8080
14.207.149.139:9080
```

## [HTTPS (539/2512)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.32.59.217:47045
5.16.0.77:1256
5.134.221.58:41890
5.180.130.90:80
5.182.208.236:8080
5.189.229.42:1081
5.202.191.226:8080
14.241.111.38:8080
27.42.168.46:55481
27.72.244.228:8080
27.131.179.207:10443
27.147.209.215:8080
31.42.184.91:1081
31.128.71.241:8081
31.204.180.44:53281
34.230.89.25:49205
36.67.150.247:8080
36.94.2.138:443
36.94.61.196:4480
36.94.161.219:8080
36.94.183.153:8080
36.95.53.227:8080
36.95.65.99:8019
36.95.79.7:41890
36.95.249.157:8080
37.53.83.237:8080
37.139.26.54:3128
41.77.13.186:53281
41.164.68.194:8080
41.174.179.147:8080
```

## [ARCHIVE (2512/16818)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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
1.2.222.252:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.161.108:4145
```



Thx Co Pure Gs - Sort Meister! 💟