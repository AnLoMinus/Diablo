 
---
 
# Anlominus PenTest Report for Google 
#### Date: Tue May 24 23:39:27 IDT 2022
 
---
 
# 📜 Menu

      [a] - Anonymity Surfing
      [1] - Planning and Scoping
      [2] - Reconnaissance & Vulnerability Assessment
      [3] - Gaining Access & Maintaining Access
      [4] - Covering tracks
      [5] - Analysis & Reporting

      ┌──[ Anlominus 👽 Diablo $~]
      └──╼

      
 
---
 
# [1] - Planning and Scoping 
### Planning Log 8.8.8.8: 
 
---
 
# [2] - Reconnaissance & Vulnerability Assessment 
 
### TraceRoute Scan Log 8.8.8.8: 
 
  1  netbox (10.100.102.1)  18.128 ms  1.433 ms  1.630 ms
 2  lo50.cbng1.ory.nv.net.il (212.143.208.119)  5.989 ms  6.142 ms  4.485 ms
 3  core1-fh-0-6-0-8-cbng2-ory-0-0-0-21.ory.nv.net.il (207.232.57.158)  4.395 ms
    core2-fh-0-1-0-7-cbng1-ory-0-0-0-20.ory.nv.net.il (207.232.57.124)  4.628 ms
    core2-fh-0-6-0-8-cbng1-ory-0-0-0-20.ory.nv.net.il (207.232.57.152)  5.046 ms
 4  core1-be11341.hfa.nv.net.il (212.143.12.80)  6.719 ms
    core2-be1392.nta.nv.net.il (212.143.12.90)  6.277 ms
    core1-be11341.hfa.nv.net.il (212.143.12.80)  6.264 ms
 5  core1-1-4-gw1.nta.nta.nv.net.il (212.143.203.24)  5.543 ms
    gw1-2-3-core1.nta.nta.nv.net.il (212.143.203.9)  5.793 ms
    gw2-0-1-core1.hfa.hfa.nv.net.il (212.143.7.245)  8.193 ms
 6  gw1-12-mrs-gw1.nta.nv.net.il (212.143.12.66)  51.688 ms  51.801 ms
    gw2-hu-4-2.lnd.nv.net.il (212.143.12.22)  66.907 ms
 7  10.10.30.1 (10.10.30.1)  58.363 ms
    10.10.70.1 (10.10.70.1)  61.553 ms  63.182 ms
 8  dns.google (8.8.8.8)  73.485 ms
    195.66.224.125 (195.66.224.125)  59.337 ms
    ipv4.de-cix.fra.de.as15169.google.com (80.81.192.108)  60.431 ms 
 
### Arp Scan Log 8.8.8.8: 
 
 ? (10.100.102.1) at 34:49:5b:5:b0:67 on en0 ifscope [ethernet]
? (10.100.102.9) at 80:6a:50:fe:8f:8f on en0 ifscope [ethernet]
? (10.100.102.33) at 64:95:6c:93:58:ba on en0 ifscope [ethernet]
? (10.100.102.53) at 84:14:4d:bb:3d:a7 on en0 ifscope [ethernet]
? (224.0.0.251) at 1:0:5e:0:0:fb on en0 ifscope permanent [ethernet]
? (239.255.255.250) at 1:0:5e:7f:ff:fa on en0 ifscope permanent [ethernet]
? (239.255.255.250) at 1:0:5e:7f:ff:fa on bridge100 ifscope permanent [ethernet]
? (239.255.255.250) at 1:0:5e:7f:ff:fa on bridge101 ifscope permanent [ethernet] 
 
### Ping Scan Log 8.8.8.8: 
 
 PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: icmp_seq=0 ttl=116 time=77.273 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=116 time=69.356 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=116 time=68.634 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=116 time=68.180 ms

--- 8.8.8.8 ping statistics ---
4 packets transmitted, 4 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 68.180/70.861/77.273/3.726 ms 
 
### Dig Scan Log 8.8.8.8: 
 
 
; <<>> DiG 9.10.6 <<>> 8.8.8.8 all
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 54985
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;8.8.8.8.			IN	A

;; ANSWER SECTION:
8.8.8.8.		0	IN	A	8.8.8.8

;; Query time: 58 msec
;; SERVER: 10.100.102.1#53(10.100.102.1)
;; WHEN: Tue May 24 23:39:35 IDT 2022
;; MSG SIZE  rcvd: 52

;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NXDOMAIN, id: 29938
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;all.				IN	A

;; AUTHORITY SECTION:
.			86400	IN	SOA	a.root-servers.net. nstld.verisign-grs.com. 2022052401 1800 900 604800 86400

;; Query time: 9 msec
;; SERVER: 10.100.102.1#53(10.100.102.1)
;; WHEN: Tue May 24 23:39:35 IDT 2022
;; MSG SIZE  rcvd: 107 
 
### Nslookup Scan Log 8.8.8.8: 
 
 Server:		10.100.102.1
Address:	10.100.102.1#53

Non-authoritative answer:
8.8.8.8.in-addr.arpa	name = dns.google.

Authoritative answers can be found from:
8.8.8.in-addr.arpa	nameserver = ns4.google.com.
8.8.8.in-addr.arpa	nameserver = ns2.google.com.
8.8.8.in-addr.arpa	nameserver = ns1.google.com.
8.8.8.in-addr.arpa	nameserver = ns3.google.com.
ns1.google.com	internet address = 216.239.32.10
ns2.google.com	internet address = 216.239.34.10
ns3.google.com	internet address = 216.239.36.10
ns4.google.com	internet address = 216.239.38.10
ns1.google.com	has AAAA address 2001:4860:4802:32::a
ns2.google.com	has AAAA address 2001:4860:4802:34::a
ns3.google.com	has AAAA address 2001:4860:4802:36::a
ns4.google.com	has AAAA address 2001:4860:4802:38::a 
 
### WhoIs Scan Log 8.8.8.8: 
 
 % IANA WHOIS server
% for more information on IANA, visit http://www.iana.org
% This query returned 1 object

refer:        whois.arin.net

inetnum:      8.0.0.0 - 8.255.255.255
organisation: Administered by ARIN
status:       LEGACY

whois:        whois.arin.net

changed:      1992-12
source:       IANA

# whois.arin.net

NetRange:       8.0.0.0 - 8.127.255.255
CIDR:           8.0.0.0/9
NetName:        LVLT-ORG-8-8
NetHandle:      NET-8-0-0-0-1
Parent:         NET8 (NET-8-0-0-0-0)
NetType:        Direct Allocation
OriginAS:       
Organization:   Level 3 Parent, LLC (LPL-141)
RegDate:        1992-12-01
Updated:        2018-04-23
Ref:            https://rdap.arin.net/registry/ip/8.0.0.0


OrgName:        Level 3 Parent, LLC
OrgId:          LPL-141
Address:        100 CenturyLink Drive
City:           Monroe
StateProv:      LA
PostalCode:     71203
Country:        US
RegDate:        2018-02-06
Updated:        2021-09-23
Comment:        ADDRESSES WITHIN THIS BLOCK ARE NON-PORTABLE ANY ISP ANNOUNCING OR TRANSITING PORTIONS WITHIN OUR RANGES SHOULD NOT RELY ON PRESENTED LOA'S UNLESS THOSE RANGES ARE ALSO ANNOUNCED TO A LUMEN ASN. 
Comment:        
Comment:        Our looking glass is located at: https://lookingglass.centurylink.com/
Comment:        
Comment:        For subpoena or court order please fax 844.254.5800 or refer to our Trust & Safety page:
Comment:        https://www.lumen.com/en-us/about/legal/trust-center/trust-and-safety.html
Comment:        
Comment:        For abuse issues, please email abuse@aup.lumen.com
Comment:        All abuse reports MUST include: 
Comment:        * src IP 
Comment:        * dest IP (your IP) 
Comment:        * dest port 
Comment:        * Accurate date/timestamp and timezone of activity 
Comment:        * Intensity/frequency (short log extracts) 
Comment:        * Your contact details (phone and email) 
Comment:        Without these we will be unable to identify the correct owner of the IP address at that point in time.
Ref:            https://rdap.arin.net/registry/entity/LPL-141


OrgTechHandle: IPADD5-ARIN
OrgTechName:   ipaddressing
OrgTechPhone:  +1-877-453-8353 
OrgTechEmail:  ipaddressing@level3.com
OrgTechRef:    https://rdap.arin.net/registry/entity/IPADD5-ARIN

OrgAbuseHandle: LAC56-ARIN
OrgAbuseName:   L3 Abuse Contact
OrgAbusePhone:  +1-877-453-8353 
OrgAbuseEmail:  abuse@level3.com
OrgAbuseRef:    https://rdap.arin.net/registry/entity/LAC56-ARIN 
 
### Dirb Scan Log 8.8.8.8: 
 
  
 
### Nmap Scan Log 8.8.8.8: 
 
