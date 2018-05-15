---
title: Preface
weight: 1
---

The data structure of the responses that deliver content data follows the HAL syntax \([http://stateless.co/hal\_specification.html\](http://stateless.co/hal_specification.html%29\) and will be closer to our internal structure than it was in the API 1.2. As the API 2.0 will take account of the request's \`Accept\` header, clients MUST set it to one of \`application/hal+json\`, \`application/json\` or \`text/json\`. Otherwise the API will respond with status code 406 ("Not Acceptable") (or, in case of a development /testing environment, with a browser-friendly dump).

TODO: Event-Titel, Biografien, Programmtexte besprechen für API 2.0

#### API Environments & Complete URLs

All endpoints in the documentation are relative URLs. The base URL depends on the environment.

Note: Besides the URL to the manifest itself, most complete URLs for subsequent calls will be found in the responses of the API. Do not dynamically build complete URLs to endpoints where it is not explicitly needed!

| Environment | Base URL |
| :--- | :--- |
| DEV | //tv-dev1.dchdev.net/v2 |
| TEST | //api-test.dchdev.net/v2 |
| LIVE | //api.digitalaconcerthall.com/v2 |



