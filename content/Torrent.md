---
title: "Torrent"
---

I've downloaded qBittorrent, used torrents from rutracker.org, but the download speed was insanely slow. I think my provider (Tele2) blocks bittorrent traffic. So I've watched [this](https://www.youtube.com/watch?v=3vASipHKEKM) video and did exactly what he did. Enabled proxy SOCKS5 with 127.0.0.1:9150 and it freakin worked!!! I didn't even download Tor or anything. In my earlier attempts to fix it I also added this to `/etc/hosts`:
```
163.172.167.207 bt.t-ru.org  
163.172.167.207 bt2.t-ru.org  
163.172.167.207 bt3.t-ru.org  
163.172.167.207 bt4.t-ru.org
```
