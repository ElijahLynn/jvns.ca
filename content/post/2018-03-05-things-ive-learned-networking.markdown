---
title: "A few things I've learned about computer networking"
date: 2018-03-05T22:39:22Z
url: /blog/2018/03/05/things-ive-learned-networking/
categories: []
---

Somebody asked a few months ago "hey, what's the best way to understand computer networking?". I
don't really know how to answer this question -- I've learned a lot of the things I know at work,
and I think picking up new things when I need them has been fine.

But I thought it could maybe be useful to list a bunch of concrete skills and concepts I've learned
along the way. Like anything else, "computer networking" involves a large number of different
concepts and skills and tools and I've learned them all one at a time.  I picked most of these
things up over the last 4 years.

- How to set up an Apache web server by copying and pasting things from the internet. (pre-2010)
- What a http request looks like (GET, POST, etc). How to use curl to send GET and POST requests.
  (2010?)
- How to send a http request by hand with netcat (2013)
- how to do [ARP spoofing](https://jvns.ca/blog/2013/10/29/day-18-in-ur-connection/) (and what ARP
  is)
- What a MAC address is and how packets are addressed to a MAC address on a local network
- How [traceroute works](https://jvns.ca/blog/2013/10/31/day-20-scapy-and-traceroute/) (which involves learning the basics of how the the IP protocol works and what a TTL is)
- What a network packet is, how to look at a networking packet with Wireshark
- The basics of how TCP works (for example by looking at an http request with wireshark, and by
  [building a tcp stack in Python](https://jvns.ca/blog/2014/08/12/what-happens-if-you-write-a-tcp-stack-in-python/)). Key things: what's a SYN packet?
- how DNS works (like, what's an A record, what's a CNAME record, what does a DNS query look like --
  wireshark is good here too).
- More HTTP (like cache headers and how they interact with CDNs). More [about what CDNs are for](https://jvns.ca/blog/2016/04/29/cdns-arent-just-for-caching/)
- MTU exists and can cause networking issues
- Having badly tuned TCP connection settings (like TCP_NODELAY) can cause noticeable networking performanace issues ([why you should understand (a little) about TCP](https://jvns.ca/blog/2015/11/21/why-you-should-understand-a-little-about-tcp/)) (2015)
- HTTP security headers like CORS
- What ["SNI" means](https://jvns.ca/blog/2016/07/14/whats-sni/)
- how to use tcpdump to debug firewall issues (2016)
- how to capture packets with `tcpdump` in somewhat weird ways (for instance "only this very
  specific kind of DNS response")
- "can reliably use tcpdump without reading the man page"
- SSL/TLS: what's a SSL cert? how do I get one issued? how is a SSL cert put together? (tools:
  `openssl x509`). [here's a blog post about TLS](https://jvns.ca/blog/2017/01/31/whats-tls/)
- more advanced HTTP+SSL stuff, like the [Strict-Transport-Security header](https://jvns.ca/blog/2017/04/30/using-strict-transport-security/)
- very basic understanding of what BGP is and how packets get routed on the internet
- slightly more advanced DNS (what's an authoritative dns server, what's a recursive dns server)
- a vague understanding of [how the linux networking stack handles packets](https://blog.packagecloud.io/eng/2016/06/22/monitoring-tuning-linux-networking-stack-receiving-data/), like -- do packets get sent to tcpdump before or after routing? (after!)
- how to [slow down my internet on purpose with tc](https://jvns.ca/blog/2017/04/01/slow-down-your-internet-with-tc/)
- how to set up NAT rules with iptables
- how to inspect a route table with iproute2
- container/docker networking (network namespaces, route tables) (2017)

### tools I've found useful

Per [this tweet](https://twitter.com/b0rk/status/851652231862595584):

* ping (are these computer connected??)
* whois (is this domain registered)
* ssh
* curl (for making HTTP requests)
* tcpdump (record packets! check for traffic on a port!)
* dig/nslookup (debugging DNS issues)
* netstat/ss (is that port being used?)
* ifconfig (what's my IP address?)
* iproute2 (that is, the `ip` command. replacement for ifconfig. very useful.)
* wireshark (look at packets with a GUI)
* ngrep (grep for your network)
* iptables
* socat (connect a unix domain socket to a tcp socket)
* `nsenter` for debugging container networking problems

### learning takes a lot of time

I spend a fair amount of time trying to learn new computer things. I've found it really useful to
take it one step at a time -- my learning process with a lot of this stuff is basically

* identify something small I don't know (how to, from the command line, check the expiration date on
  https://google.com's TLS certificate)
* figure it out (sometimes with help from my great coworkers)
* repeat

That's all! It's really fun to see how learning a bunch of tiny things adds up over time. Like today
I feel like I can handle most things about computer networking that I run into in my job, and I
don't feel like there are that many Big New Ideas about networking I don't know about. (though,
well, wifi is still a mystery to me :) )
