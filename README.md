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

# [SAMPLE PROXIES] - [July 24 2022 | 03:04:06]

### Proxy Statistics:
- _Online Proxies (By Protocol):_
   - **SOCKS4** -> 2976
   - **SOCKS5** -> 329
   - **HTTP** -> 2271
   - **HTTPS** -> 2127

- _Proxies (Total):_
   - **Online Proxies (SOCKS4/5 + HTTP/S)** -> 5112
   - **Unique Online Proxies** -> 5112
   - **Unique Online/Offline Proxies (Archive)** -> 13756

## [SOCKS4 (2976/5112)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks4.txt)
```yaml
1.0.132.249:4153
1.0.133.100:51327
1.4.195.114:4145
1.4.214.148:5678
1.9.167.36:60489
1.9.213.114:4153
1.10.140.43:4145
1.10.141.220:54620
1.10.189.133:50855
1.20.95.95:5678
1.20.96.30:4153
1.20.137.82:32241
1.20.184.75:4153
1.20.220.79:4145
1.20.227.66:4145
1.32.57.85:5678
1.32.59.217:47045
1.53.137.84:4145
1.55.241.4:4145
1.179.130.201:4153
1.179.148.9:36476
1.179.151.165:31948
1.179.173.114:4153
1.186.40.2:39651
1.186.40.177:39651
1.186.85.74:5678
1.186.139.9:39651
1.186.213.67:5678
1.220.145.45:4145
1.221.173.148:4145
```

## [SOCKS5 (329/5112)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-socks5.txt)
```yaml
1.180.0.162:7302
1.180.49.222:7302
3.131.207.170:13343
3.211.17.212:80
5.128.61.28:1080
5.130.89.32:1080
5.161.86.206:1080
5.161.93.53:1080
5.161.100.145:1080
5.188.199.5:1080
8.209.220.34:80
8.210.18.98:27831
13.59.58.111:1080
15.185.227.31:8080
20.230.193.232:80
20.239.2.157:80
24.249.199.4:4145
24.249.199.12:4145
31.128.248.1:1080
31.128.248.2:1080
35.244.6.175:1080
36.89.86.49:56845
37.59.98.31:9050
37.131.202.95:33427
39.108.56.233:38080
42.194.130.58:10808
43.128.36.71:3389
43.129.95.244:8080
43.129.207.123:3001
43.135.74.226:38081
```

## [HTTP (2271/5112)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-http.txt)
```yaml
1.0.170.50:80
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.10.141.220:54620
1.20.166.142:8080
1.20.217.52:8080
1.32.59.217:47045
1.179.136.98:8080
1.179.144.41:8080
1.179.148.9:36476
1.186.85.2:1111
2.179.193.146:80
2.188.164.194:8080
3.20.236.208:49205
3.215.177.148:49205
5.9.112.247:3128
5.16.0.97:1256
5.16.0.174:8080
5.16.0.180:8080
5.16.1.17:8080
5.22.196.30:8080
5.44.62.166:8080
5.58.33.187:55507
5.167.141.239:3128
5.188.136.52:8080
8.215.27.71:3128
8.242.207.202:8080
12.144.254.185:9080
```

## [HTTPS (2127/5112)](https://raw.githubusercontent.com/jetkai/proxy-list/main/online-proxies/txt/proxies-https.txt)
```yaml
1.0.170.50:80
1.0.205.87:8080
1.1.189.58:8080
1.1.220.100:8080
1.2.252.65:8080
1.10.141.220:54620
1.20.166.142:8080
1.20.217.52:8080
1.32.59.217:47045
1.179.136.98:8080
1.179.144.41:8080
1.179.148.9:36476
1.186.85.2:1111
2.179.193.146:80
2.188.164.194:8080
3.20.236.208:49205
3.215.177.148:49205
5.9.112.247:3128
5.16.0.97:1256
5.16.0.174:8080
5.16.0.180:8080
5.16.1.17:8080
5.22.196.30:8080
5.44.62.166:8080
5.58.33.187:55507
5.167.141.239:3128
5.188.136.52:8080
8.242.207.202:8080
12.144.254.185:9080
12.218.209.130:13326
```

## [ARCHIVE (5112/13756)](https://raw.githubusercontent.com/jetkai/proxy-list/main/archive/txt/working-proxies-history.txt)
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