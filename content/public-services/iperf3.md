---
title: iPerf3
---

An [Nmap](https://nmap.org/) service detection scan shows that an [iPerf3](https://en.wikipedia.org/wiki/Iperf) server is listening on port `5201` of IP addresses `199.167.59.4` and `199.167.59.5`:

{{< highlight shell >}}
$ nmap -Pn -n -p 5201 -sV 199.167.59.4,5
Starting Nmap 7.80 ( https://nmap.org ) at 2019-09-06 18:17 EDT
Nmap scan report for 199.167.59.4
Host is up (0.16s latency).

PORT     STATE SERVICE VERSION
5201/tcp open  iperf3

Nmap scan report for 199.167.59.5
Host is up (0.16s latency).

PORT     STATE SERVICE VERSION
5201/tcp open  iperf3

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 2 IP addresses (2 hosts up) scanned in 82.38 seconds
{{< /highlight >}}
