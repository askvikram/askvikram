---
id: 3884
title: 'How to Find IP address(Public &#038; Private) Using SSH Commands?'
date: '2020-12-27T22:21:22+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3884'
permalink: /find-ip-address-public-private/
rank_math_seo_score:
    - '70'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
ss_social_share_disable:
    - '0'
rank_math_internal_links_processed:
    - '1'
rank_math_primary_category:
    - '16'
rank_math_focus_keyword:
    - 'find ip address'
rank_math_description:
    - 'In this tutorial, you''ll find IP address (Internal and External) of your computer. Internal and External IP address also known as private and public IP address respectively. '
socialsnap_share_count_timestamp:
    - '2023-09-13 20:53:27'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '17'
categories:
    - how-to
tags:
    - tutorials
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

IP address is a unique numerical label assigned to your computer or a hardware connected to the network. With the IP address, you can easily communicate with that computer over the network.

There are two types of IP address. Public IP address and Private IP address. These address are also called as external IP address and Internal IP address respectively.

Public IP address or an external IP address is an address used to identify a computer on a public network(Internet).

Private IP address or an internal IP address is an address used to identify a computer in a private network/private subnet.

In this tutorial, you’ll learn how to find IP address (Internal and External) of your computer using SSH Command line.

## <span class="ez-toc-section" id="finding_ip_address_using_ssh_command"></span>Finding IP Address Using SSH Command<span class="ez-toc-section-end"></span>

### Finding Internal IP Address

In this section, you’ll learn how to find Internal Ip address or a private ip address.

If you would like to see your IP without any additional network details, you can use the <mark>hostname -I</mark> command. Hostname is a name given to a computer present on the internet. -I is the flag used to get the *IP address* of the hostname.

```
<pre class="wp-block-code">```
hostname -I
```
```

Output

```
<pre class="wp-block-code config">```
172.35.18.67
```
```

To find the ip address along with some additional details, you need to install the package <mark>net-tools</mark> from the ubuntu package management system. Use the below command to install <mark>net-tools</mark>.

This package is deprecated and some linux distributions are not including it by default.

```
<pre class="wp-block-code">```
sudo apt install net-tools
```
```

Net tools is installed.

You can use ifconfig -a command to find the IP address.

Ifconfig is a system administration utility for the network interfaces of the unix based systems. This will give you all relevant details along with the IP address.

```
<pre class="wp-block-code">```
ifconfig -a
```
```

Output

```
<pre class="wp-block-code config">```
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet <var>172.35.18.67</var>  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::8ed:32ff:fee5:c27c  prefixlen 64  scopeid 0x20<link>
        ether 0a:ed:32:e5:c2:7c  txqueuelen 1000  (Ethernet)
        RX packets 695251  bytes 419990425 (419.9 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 571188  bytes 124132653 (124.1 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 269127  bytes 90758338 (90.7 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 269127  bytes 90758338 (90.7 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```
```

The highlighted text is your internal IP address.

These are the different methods available to find the internal or private IP address of your Linux machines.

Next, you’ll find the external or public IP address of your computer.

### Finding External IP Address

In this section, you’ll find the external or the public IP address of your computer.

You’ll be able to **find the public IP address using <mark>ifconfig</mark> if your computer is not configured via router**. However, this’ll not help when you’re connected with the router. You need to use an external service or a DNS resolver to find the IP address.

### Using an External Service

You can use any external service provider like <mark>checkip.amazonaws.com</mark> to determine your IP address. Amazon AWS is a well known service provider which is unlikely to go down anytime soon.

To use this service from the command line, you can use it along with the <mark>curl</mark> command. <mark>curl</mark> is a command line tool which is used to transfer data to and from server.

When it is used along with the *checkip.amazonaws.com*, it will print the IP address of your computer using the plain text returned in the response body.

```
<pre class="wp-block-code">```
curl https://checkip.amazonaws.com
```
```

Output

```
<pre class="wp-block-code config">```
172.35.18.67
```
```

### Using a DNS Resolver

You can find the external IP address using a DNS resolver. The advantage of using a DNS resolver over the external services are, DNS resolver are standard ones. The Google public DNS servers and Open DNS are more stable and scalable ones. They will exist until the internet exists. Hence **its highly recommended to use the DNS resolvers if you are using a script to find the IP address and plug it into your programs.**

You can use the [dig](https://ss64.com/bash/dig.html) command to find the external IP address. It is a **D**omain **I**nformation **G**roper command which can be used to interrogate the domain name servers.

Use the below command to find the external IP address using the dig command.

```
<pre class="wp-block-code">```
dig @resolver4.opendns.com myip.opendns.com +short
```
```

- **dig** – keyword
- **@resolver4.opendns.com** – specifies the openDNS to be used
- **myip.opendns.com** – specifies MYIP to be written
- **+short** – specifies the Ip address should be returned in a short form

Output

```
<pre class="wp-block-code">```
13.275.54.28
```
```

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you have learnt how to find IP address (private or internal) and (public or external) IP address of your computer.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1609088570308">### How do I find my IP address in Linux terminal?

<div class="rank-math-answer ">You can use <mark>hostname -I</mark> to find your IP address in Linux Terminal.

</div></div></div></div>