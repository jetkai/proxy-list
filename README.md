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

# [SAMPLE PROXIES] - [October 20 2021 | 09:29:03]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2855
   - **SOCKS5** -> 248
   - **HTTP** -> 380
   - **HTTPS** -> 393

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3876
   - **Unique Online Proxies** -> 3681
   - **Unique Online/Offline Proxies (Archive)** -> 21462

## [SOCKS4 (2855/3681)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.100:51327
1.4.154.110:5678
1.4.157.35:36202
1.4.214.148:5678
1.9.71.4:4153
1.9.164.242:35471
1.9.167.36:60489
1.14.104.146:1080
1.20.95.95:5678
1.20.96.164:4153
1.20.99.41:5678
1.20.203.14:4145
1.32.57.85:5678
1.55.241.4:4145
1.71.133.58:5678
1.179.147.5:52210
1.179.148.9:36476
1.186.40.157:39651
1.186.139.9:39651
1.212.181.131:4145
2.135.223.134:5678
2.139.162.80:4145
2.183.8.145:4153
3.141.13.98:5678
5.22.154.50:32127
5.34.74.214:4145
5.56.133.204:4444
5.58.47.25:3629
5.83.94.194:4153
5.83.104.143:4153
```

## [SOCKS5 (248/3681)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
3.133.40.194:8080
5.34.247.215:12356
5.56.134.237:45698
5.164.23.101:1080
8.129.8.2:9999
8.210.251.244:24691
13.250.172.147:48540
27.76.10.118:5005
27.116.51.178:6667
27.122.57.227:3128
31.128.248.1:1080
31.128.248.2:1080
31.186.241.7:52185
35.201.142.139:10004
35.201.142.139:10002
36.90.108.111:1080
37.52.48.238:8888
37.156.104.178:3327
37.187.72.30:57257
43.224.8.12:6667
43.224.8.14:6667
43.224.8.116:6667
43.224.10.8:6667
43.224.10.13:6667
43.224.10.26:6667
43.224.10.30:6667
43.224.10.33:6667
43.224.10.35:6667
43.224.10.43:6667
43.224.10.46:6667
```

## [HTTP (380/3681)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.20.99.122:8080
1.116.4.222:7890
1.116.12.21:3228
2.188.166.25:3128
5.56.134.237:55963
5.227.65.88:3128
8.129.129.23:9999
8.142.75.137:3128
8.208.91.118:8888
8.208.91.118:8081
14.192.2.161:83
14.207.126.195:8080
14.207.178.223:8080
14.241.225.167:443
18.159.210.15:9300
20.206.77.128:8080
24.154.200.232:8080
27.116.51.178:6666
27.116.63.120:7999
27.128.242.141:8089
27.191.60.194:3256
31.14.126.82:9090
34.87.0.241:3128
34.138.225.120:8888
34.212.203.168:8800
36.66.206.74:8080
36.67.73.129:8080
36.89.190.85:8080
36.89.192.115:53219
36.92.85.66:8080
```

## [HTTPS (393/3681)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.116.12.21:3228
2.188.166.22:3128
2.188.166.25:3128
5.200.72.51:3128
14.161.10.191:8080
18.159.210.15:9300
20.206.77.128:8080
27.22.85.58:8100
27.105.130.93:8080
27.128.242.141:8089
27.131.179.197:10443
31.172.177.149:83
34.138.225.120:8888
35.206.150.95:3128
36.66.171.243:8080
36.67.152.213:11111
36.94.133.138:8080
36.94.172.187:6969
36.255.86.114:82
37.26.86.206:47464
39.96.29.123:8080
39.108.111.52:3228
39.108.246.51:3228
39.108.246.242:3228
41.65.162.75:1981
41.220.238.130:82
41.221.158.186:31932
42.194.186.119:8081
43.135.130.68:8080
43.224.8.14:6666
```

## [ARCHIVE (3681/21462)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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