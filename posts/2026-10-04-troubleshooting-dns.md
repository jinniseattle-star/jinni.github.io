---

layout: post
title: "Troubleshooting DNS: When an IP Address Works but a Domain Does Not"
date: 2026-10-04 19:00:00 -0700
categories: [Networking, Troubleshooting]
-----------------------------------------

## The Objective

This week, I practiced basic network troubleshooting and learned how to investigate connectivity problems using command-line tools.

One important troubleshooting scenario is when a computer can reach an IP address but cannot reach a destination using its domain name. Understanding the difference helps narrow down the possible cause instead of assuming the entire Internet connection is down.

## The Hurdle

Consider this scenario: `ping 1.1.1.1` succeeds, but `ping google.com` fails.

An IP address is already a numerical network address, so DNS is not needed to translate it. However, a domain name such as `google.com` normally needs to be resolved to an IP address before the computer can communicate with that destination.

This suggests that DNS could be the problem, but it does not prove it. A failed ping can also result from ICMP traffic being blocked or other connectivity issues.

## The Solution

I can use `nslookup` to investigate DNS resolution:

```bash
nslookup google.com
```

This command queries a DNS server to find the IP address associated with the domain name. Its output also helps identify which DNS server is being used.

I would check whether the query returns an answer or an error. If DNS resolution fails, I would investigate the DNS server configuration and availability. If it succeeds, I would continue troubleshooting other possible causes of the failed ping.

## What I Learned

The main lesson is to troubleshoot systematically instead of jumping to conclusions.

When investigating a connectivity problem, I can ask:

1. Can the computer reach a known IP address?
2. Can it resolve a domain name using DNS?
3. Is the DNS server responding correctly?
4. If DNS works, what other network issue could explain the failure?

**Future me:** When a domain name fails but an IP address works, use `nslookup` to investigate DNS before deciding what is broken. Always verify the results instead of assuming the cause.
