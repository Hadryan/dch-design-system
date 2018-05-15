---
title: Language Support
weight: 2
---

Language specific versions will be determined by the client's `Accept-Language` header. If the set language is not supported by our service, it falls back to English. In most cases, this will deliver the correct language preferred by the user with no effort from the client itself. However, if a client wants to have full control of the language that will be delivered, it can set the `Accept-Language` header manually.