---
author: vhorne
ms.service: application-gateway
ms.topic: include
ms.date: 09/09/2021
ms.author: victorh
---
| Resource | Limit | Note |
| --- | --- | --- |
| Azure Application Gateway |1,000 per subscription | |
| Front-end IP configurations |2 |1 public and 1 private |
| Front-end ports |100<sup>1</sup> | |
| Back-end address pools |100<sup>1</sup> | |
| Back-end servers per pool |1,200 | |
| HTTP listeners |200<sup>1</sup> |Limited to 100 active listeners that are routing traffic. Active listeners = total number of listeners - listeners not active.<br>If a default configuration inside a routing rule is set to route traffic (for example, it has a listener, a backend pool, and HTTP settings) then that also counts as a listener. See [Frequently asked questions about Application Gateway](../articles/application-gateway/application-gateway-faq.yml#what-is-considered-an-active-listener-versus-inactive-listener) for additional details.|
| HTTP load-balancing rules |400<sup>1</sup> | |
| Back-end HTTP settings |100<sup>1</sup> | |
| Instances per gateway |V1 SKU - 32<br>V2 SKU - 125 | |
| SSL certificates |100<sup>1</sup> |1 per HTTP listener |
| Maximum SSL certificate size |V1 SKU - 10 KB<br>V2 SKU - 16 KB| |
| Authentication certificates |100 | |
| Trusted root certificates |100 | |
| Request timeout minimum |1 second | |
| Request timeout maximum to private backend |24 hours | |
| Request timeout maximum to external backend |4 minutes | |
| Number of sites |100<sup>1</sup> |1 per HTTP listener |
| URL maps per listener |1 | |
| Maximum path-based rules per URL map|100||
| Redirect configurations |100<sup>1</sup>| |
| Number of rewrite rule sets |400| |
| Number of Header or URL configuration per rewrite rule set|40| |
| Number of conditions per rewrite rule set|40| |
| Concurrent WebSocket connections |Medium gateways 20k<sup>2</sup><br> Large gateways 50k<sup>2</sup>| |
| Maximum URL length|32KB| |
| Maximum header size|32KB| |
| Maximum header field size for HTTP/2|8KB| |
| Maximum header size for HTTP/2|16KB| |
| Maximum file upload size (Standard SKU) |V2 - 4 GB<br>V1 - 2GB | |
| Maximum file upload size (WAF SKU) |V1 Medium - 100 MB<br>V1 Large - 500 MB<br>V2 - 750 MB<br>V2 (with CRS 3.2 or newer) - 4GB| |
| WAF body size limit (without files)|V1 or V2 (with CRS 3.1 and older) - 128KB<br>V2 (with CRS 3.2 or newer) - 2MB| |
| Maximum WAF custom rules|100||
| Maximum WAF exclusions per Application Gateway|40||

<sup>1</sup> In case of WAF-enabled SKUs, you must limit the number of resources to 40.

<sup>2</sup> Limit is per Application Gateway instance not per Application Gateway resource.
