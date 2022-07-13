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

# 🎁 SOCKS4/5 & HTTP/S PROXIES // ONLINE + ARCHIVE

[![Commits][commit-shield]][commit-url]
[![Commits][commit-activity]][commit-activity-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

###### Major update -> 29/05/2022 | [ProxyBuilder 2.0](https://github.com/jetkai/proxy-builder-2)
###### Previous version -> 22/07/2021 - 28/05/2022 | [ProxyBuilder 1.0](https://github.com/jetkai/ProxyBuilder)

## 📰About This Project & The Proxies
This repository contains a free list of tested SOCKS4/5 & HTTP/S proxies in -> **JSON**, **TXT**, **CSV**, **XML** & **YAML** format. No authentication is required when connecting to these proxies.

## 👩‍💻Proxy Testing

These proxies are tested ~12x/day (every 2 hours) against EU/US hosting providers - **see below**, they have been verified to write & read data <**AT THE TIME OF TESTING**>.

**Hosting Provider**|**Country**|**Continent**
:-----:|:-----:|:-----:
OVH|France|EU
Amazon Web Services|United States|NA
Oracle Cloud|United Kingdom, Japan|EU, AS
Microsoft Azure|Hong Kong|AS

[Source Code](https://github.com/jetkai/proxy-builder-2/blob/master/src/main/kotlin/pe/proxy/proxybuilder2/net/proxy/tester/ProxyConnect.kt)
```kotlin
    //Netty4 Connect Example
    private fun connect(proxyData : ProxyChannelData) {
        val endpoint = proxyData.endpointServer ?: return
        val awaitTime = (if(pause.get()) 30000 else config.connectAwait)

        Bootstrap().group(workerGroup)
            .channel(NioSocketChannel::class.java)
            .resolver(NoopAddressResolverGroup.INSTANCE)
            .option(ChannelOption.AUTO_READ, proxyData.autoRead)
            .option(ChannelOption.TCP_NODELAY, true)
            .option(ChannelOption.CONNECT_TIMEOUT_MILLIS, config.timeout)
            .handler(ProxyChannelInitializer(proxyData))
            .connect(InetSocketAddress(endpoint.ip, endpoint.port))
            .channel().closeFuture().awaitUninterruptibly(awaitTime)
    }
```

## 📝Proxy Formatting

These proxies are scraped from various sources & I compile this data using my [ProxyBuilder](https://github.com/jetkai/ProxyBuilder) application. Proxies are sorted from lowest to highest 0-255 & duplicated proxies are removed — the only exception is if an IP has a different port open, which is also a working proxy tunnel <**Less than 1% of the total proxies at the time of testing**>.

```IP:Port -> 1.0.132.249:4153```

## ✔Compatability

These proxies should work for any application that can establish an HTTP, HTTPS, SOCKS4 or SOCKS5 connection. Such as, an application that has proxy support (FireFox, Chrome), or as an example, these Java Apps below. 

- [JaySyiPker](https://github.com/JayArrowz/JaySyiPker)
- [Bruteforce-RSPS](https://github.com/jetkai/Bruteforce-RSPS)
- [718 Cheat Client (Final)](https://github.com/jetkai/718-Cheat-Client-Final)

## 🔗ProxyList Links (Direct URL)

###### Classic View (IP:Port Only)

- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies.json), [**TXT**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies.txt), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies.yaml)

- _Online/Offline Proxies (Archive):_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/proxies.json), [**TXT**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/proxies.txt), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/proxies.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/proxies.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/proxies.yaml)

###### Basic View (Without Country/Statistics)

- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies-basic.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies-basic.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies-basic.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies-basic.yaml)

###### Advanced View (With Country/Statistics)
- _Online Proxies:_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/json/proxies-advanced.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/csv/proxies-advanced.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/xml/proxies-advanced.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/yaml/proxies-advanced.yaml)

- _Online/Offline Proxies (Archive):_
[**JSON**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/json/proxies-archive.json), [**CSV**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/csv/proxies-archive.csv), [**XML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/xml/proxies-archive.xml), [**YAML**](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/yaml/proxies-archive.yaml)

---

# [SAMPLE PROXIES] - [July 13 2022 | 01:34:06]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2079
   - **SOCKS5** -> 309
   - **HTTP** -> 1482
   - **HTTPS** -> 1392

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 3451
   - **Unique Online Proxies** -> 3451
   - **Unique Online/Offline Proxies (Archive)** -> 13627

## [SOCKS4 (2079/3451)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.133.89:4153
1.4.214.148:5678
1.9.167.36:60489
1.9.213.114:4153
1.10.141.220:54620
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.220.79:4145
1.20.227.66:4145
1.32.57.85:5678
1.32.59.217:47045
1.55.241.4:4145
1.179.130.201:4153
1.179.151.165:31948
1.179.173.114:4153
1.186.213.67:5678
1.221.173.148:4145
2.139.162.80:4145
3.141.13.98:5678
3.211.17.212:80
5.8.240.91:4153
5.22.154.50:32127
5.58.33.187:55507
5.58.66.55:14888
5.83.94.8:4153
5.135.24.186:808
5.161.93.53:1080
5.165.2.223:3629
```

## [SOCKS5 (309/3451)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.0.162:7302
3.211.17.212:80
5.11.17.230:1080
5.161.86.206:1080
5.161.93.53:1080
5.161.100.145:1080
8.136.192.43:80
8.209.220.34:80
8.210.18.98:27831
8.210.210.94:27832
13.59.58.111:1080
14.23.62.59:7300
14.149.69.217:7300
20.230.193.232:80
20.239.2.157:80
24.249.199.4:4145
24.249.199.12:4145
27.128.206.18:7302
31.43.203.100:1080
31.128.248.1:1080
35.244.6.175:1080
36.89.86.49:56845
37.18.73.60:5566
37.18.73.94:5566
37.131.202.95:33427
37.192.253.250:1080
39.108.56.233:38080
43.128.36.71:3389
43.129.95.244:8080
43.129.207.123:3001
```

## [HTTP (1482/3451)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.205.87:8080
1.10.141.220:54620
1.32.59.217:47045
1.179.136.98:8080
1.179.144.41:8080
1.186.85.38:1111
2.179.193.146:80
2.188.164.194:8080
3.20.236.208:49205
3.85.7.155:8083
3.215.177.148:49205
5.16.0.97:1256
5.16.0.180:8080
5.16.1.17:8080
5.44.62.166:8080
5.58.33.187:55507
5.167.141.239:3128
8.218.213.95:10809
12.88.29.66:9080
12.144.254.185:9080
12.218.209.130:13326
14.20.235.221:808
14.143.172.238:8080
14.161.43.121:8080
14.170.154.193:19132
14.241.39.165:19132
14.241.111.38:8080
14.241.225.134:443
14.248.80.77:8080
18.216.72.10:5678
```

## [HTTPS (1392/3451)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.205.87:8080
1.10.141.220:54620
1.32.59.217:47045
1.179.136.98:8080
1.179.144.41:8080
1.186.85.38:1111
2.179.193.146:80
2.188.164.194:8080
3.20.236.208:49205
3.85.7.155:8083
3.215.177.148:49205
5.16.0.97:1256
5.16.0.180:8080
5.16.1.17:8080
5.44.62.166:8080
5.58.33.187:55507
5.167.141.239:3128
8.218.213.95:10809
12.88.29.66:9080
12.144.254.185:9080
12.218.209.130:13326
14.143.172.238:8080
14.161.43.121:8080
14.170.154.193:19132
14.241.39.165:19132
14.241.111.38:8080
14.241.225.134:443
14.248.80.77:8080
18.216.72.10:5678
18.222.17.49:49205
```

## [ARCHIVE (3451/13627)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
```yaml
1.0.132.249:4153
1.0.133.89:4153
1.0.133.100:51327
1.0.136.172:4145
1.0.137.61:4153
1.0.170.50:80
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.2.180.111:4145
1.2.252.65:8080
1.4.157.35:36202
1.4.195.114:4145
1.4.198.182:4153
1.4.214.148:5678
1.9.167.35:60489
1.9.167.36:60489
1.9.213.114:4153
1.10.133.211:4145
1.10.140.43:4145
1.10.141.220:54620
1.10.189.133:50855
1.13.21.26:33080
1.13.165.87:8080
1.14.194.51:6006
1.20.95.95:5678
1.20.96.30:4153
1.20.96.164:4153
1.20.137.82:32241
1.20.166.142:8080
```



Thx Co Pure Gs - Sort Meister! 💟