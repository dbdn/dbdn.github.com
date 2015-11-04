---
layout: post
title: 创建apns推送证书命令
category: apns
date: 2015-10-29
---

---

    openssl x509 -in aps_production.cer -inform DER -out aps_production_identity.pem -outform PEM
    openssl pkcs12 -nocerts -out PushChatKey.pem -in apns_production.p12
    cat aps_production_identity.pem PushChatKey.pem > cert.pem

<!-- more -->


![pic](/res/img/blog/apns.jpg)

