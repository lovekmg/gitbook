---
description: ssl 인증서의 만료일을 확인할수 있다
---

# openssl을 이용한 ssl 인증서 만료일 확인

## 1. Command

domain은 test.com 이라고 가정한다.(맨앞 $ 이후부터 복사할것)

```
$ $(which openssl) s_client -servername test.com -connect test.com:443 > /tmp/checkSslExpire.crt

$ $(which openssl) x509 -in /tmp/checkSslExpire.crt -noout -enddate

$ openssl x509 -in /tmp/checkSslExpire.crt -noout -enddate
notAfter=Apr  5 15:15:12 2022 GMT

$ rm /tmp/checkSslExpire.crt

```



{% hint style="info" %}
 cli에서는 파이프(|)를 이용해서 처리해도 될거 같다.
{% endhint %}

