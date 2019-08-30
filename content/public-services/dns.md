---
title: Domain name resolution (DNS)
---

The [Domain Name System (DNS)](https://en.wikipedia.org/wiki/Domain_Name_System) is a mechanism by which domain names, such as `nycmesh.net`, are translated to IP addresses, such as `104.198.14.52`. By asking questions of a DNS server, you can find out the network address belonging to a computer that has a given name, much like looking up a phone number for your friend in an address book application (or "yellow pages," back in the day). This process in which a name is translated to an address is called *name resolution*.

NYC Mesh operates a public domain name resolution service (DNS server) for anyone in the world at `199.167.59.10`. It performs no logging of domain name queries and no filtering of query responses. It is configured as a *recursive* resolver, meaning that if you ask it a question to which it does not already know the answer, it will look up the answer for you by asking other DNS servers that it knows about. In the following example, we [use the `nslookup` command-line tool](https://explainshell.com/explain?cmd=nslookup+google.com+199.167.59.10) to ask NYC Mesh's public DNS resolver for the IP address of `google.com` (shown as line 1), and receive an answer from it (shown in lines 5 through 7):

{{< highlight shell "linenos=inline" >}}
$ nslookup google.com 199.167.59.10
Server:         199.167.59.10
Address:        199.167.59.10#53

Non-authoritative answer:
Name:   google.com
Address: 172.217.12.142
{{< /highlight >}}

This name resolution procedure is something your computer usually does for you automatically whenever you use a domain name anywhere within a program, such as a Web browser's location bar.

## Public resolution of private IP addresses

In addition to resolving publicly accessible domains, the NYC Mesh public DNS resolver will also provide the private IP addresses of NYC Mesh's [intra-mesh services]({{< relref "intra-mesh-services" >}}) that have been registered with [our internal DNS service]({{< relref "network-design/dns" >}}).

Intra-mesh services are sometimes given domain names that end in `.mesh` in order to make them easier for NYC Mesh members to remember and access. Only computers that are connected to NYC Mesh's mesh network can connect to these "dot-mesh domains," but their names and IP addresses are available to the public via the public DNS resolver. To look them up, append `.nycmesh.net` to the intra-mesh service's domain name.

For example, our internal DNS server is given the dot-mesh domain name, `dns.mesh`, but thanks to the public DNS resolver, it is also available at `dns.mesh.nycmesh.net`:

{{< highlight shell "linenos=inline" >}}
$ nslookup dns.mesh.nycmesh.net 199.167.59.10
Server:         199.167.59.10
Address:        199.167.59.10#53

Non-authoritative answer:
Name:   dns.mesh.nycmesh.net
Address: 10.10.10.10
{{< /highlight >}}

Notice on line 7 that the answer we received from the public DNS resolver was a *private* IP address (`10.10.10.10`). This means that unless we are connected to the NYC Mesh network itself, we won't actually be able to speak directly to this computer. However, if we are connected to the NYC Mesh network ourselves, then we can access this same computer at both of its names: `dns.mesh` and `dns.mesh.nycmesh.net`.
