# linux-global-ipid-patch
A patch for Linux kernel 6.x to enable global IP ID behavior.

## What is global IP ID?
Originally used to assist network-layer fragmentation and reassembly, the IP identification field (IP-ID) has been used and abused for a range of tasks, from counting hosts behind NAT, to detect router aliases and, lately, to assist detection of censorship in the Internet at large. These inferences have been possible since, in the past, the IP- ID was mostly implemented as a simple packet counter: however, this behavior has been discouraged for security reasons and other policies, such as random values, have been suggested.

## What can this patch do?
It can bring back the global IP ID counter which is set in each network namespace and use that counter as the IP ID value to send IP v4 packets wherever possible.
This patch is intended for research use only.

## Alternatives
Older Windows OS (like XP)
FreeBSD 13 with ip_do_randomid and ip_rfc6864 disabled on a single-threaded machine.