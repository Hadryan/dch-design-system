---
title: Web servers
weight: 1
---


**TODO: Explain environments:**
LIVE, TEST, DEV 

Quicklink: https://admin.digitalconcerthall.com/tmp_Serveruebersicht/dchserver.html

### Website

| Environment                   | Url                                      |
| ----------------------------- | ---------------------------------------- |
| LIVE über  Cloudfront         | https://www.digitalconcerthall.com       |
| LIVE Origin über Loadbalancer | https://origin.digitalconcerthall.com    |
| LIVE WEB 1                    | https://www-1.aws.digitalconcerthall.com |
| LIVE WEB 2                    | https://www-2.aws.digitalconcerthall.com |
| LIVE WEB 3                    | https://www-3.aws.digitalconcerthall.com |
| LIVE WEB 4                    | https://www-4.aws.digitalconcerthall.com |
| TEST                          | https://www-test.dchdev.net/admin        |
| DEV1                          | https://www-dev1.dchdev.net/admin        |


### API

| Environment                    | Url with v1.2                                                |
| ------------------------------ | ------------------------------------------------------------ |
| LIVE via Cloudfront            | https://api.digitalconcerthall.com/v1.2/static/manifest-en   |
| LIVE Origin  über Loadbalancer | https://api-origin.digitalconcerthall.com/v1.2/static/manifest-en |
| LIVE WEB 1                     | https://tv-1.aws.digitalconcerthall.com/v1.2/static/manifest-en |
| LIVE WEB 2                     | https://tv-2.aws.digitalconcerthall.com/v1.2/static/manifest-en |
| TEST via Cloudfront            | https://api-test.dchdev.net/v1.2/static/manifest-en          |
| TEST via Loadbalancer          | https://api-origin-test.dchdev.net/v1.2/static/manifest-en   |
| DEV1                           | https://tv-dev1.dchdev.net/v1.2/static/manifest-en           |


### DCH Admin 

| Environment | Url                                  |
| ----------- | ------------------------------------ |
| LIVE        | https://admin.digitalconcerthall.com |
| TEST        | https://admin-test.dchdev.net        |
| DEV1        | https://admin-dev1.dchdev.net        |


### Drupal

| Environment | Url                                     |
| ----------- | --------------------------------------- |
| LIVE via LB | https://drupal.digitalconcerthall.com   |
| LIVE WEB 1  | https://be-1.aws.digitalconcerthall.com |
| LIVE WEB2   | https://be-2.aws.digitalconcerthall.com |
| TEST        | https://be-test.dchdev.net              |
| DEV1        | https://be-dev1.dchdev.net              |


### Magento

| Environment | Url                                          |
| ----------- | -------------------------------------------- |
| LIVE        | https://magento.digitalconcerthall.com/admin |
| TEST        | https://rec-test.dchdev.net/admin            |
| DEV1        | https://rec-dev1.dchdev.net/admin            |


### Recordings Label Website

| Environment | Url                                                |
| ----------- | -------------------------------------------------- |
| LIVE        | https://www.berliner-philharmoniker-recordings.com |
| TEST        | https://rec-test.dchdev.net                        |
| DEV1        | https://rec-dev1.dchdev.net                        |

### Institutions Shop

| Environment | Url                                              |
| ----------- | ------------------------------------------------ |
| LIVE        | https://institutions-shop.digitalconcerthall.com |
| TEST        | https://institutions-shop-test.dchdev.net        |
| DEV1        | https://institutions-shop-dev1.dchdev.net        |

---

## Zugriff auf die DCH-Infrastruktur per VPN

Die bei AWS gehosteten VMs sind nur in wenigen Fällen noch direkt von außen erreichbar. Konkret können DEV-Systeme mit einer festen (Elastic) IP per Security Group bei Bedarf so konfiguriert werden, dass sie von festen, bekannten externen IPs per SSH erreicht werden können. Alle anderen Systeme, insbesondere TEST-, LIVE- und Datenbankserver sind aber nur via VPN erreichbar.

Für größtmögliche Kompatibilität und Einfachheit in Einrichtung und Nutzung wird der VPN-Zugang zu den DCH-Systemen bei AWS über OpenVPN (https://openvpn.net/index.php/open-source.html) realisiert. Jeder Client, der Zugang benötigt, loggt sich via OpenVPN von einem beliebigen externen Ort auf dem DCH-OpenVPN-Server ein und kann über diese Verbindung dann alle Systeme auf den freigeschalteten Ports (insbesondere auch SSH) erreichen.

Für die Verbindung zum OpenVPN-Server benötigt man einen aktuellen OpenVPN-Client  sowie fünf Dateien, die man von SkyGate bzw. BPhil Media erhält und die ins „config“ Verzeichnis des OpenVPN Clients kopiert werden müssen:

-	Dchawsvpn.ovpn (Konfigurationsdatei für das VPN)
-	Dch_ta.key
-	Persönlicher Key und Zertifikat (.key, .crt)
-	Ca.crt (Zertifikat der Zertifizierungsinstanz von SkyGate)

**Achtung: Zertifikate sind jeweils nur ein Jahr gültig und müssen dann verlängert werden!**

