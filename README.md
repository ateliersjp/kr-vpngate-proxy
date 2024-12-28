# kr-vpngate-proxy

[VPNGate](http://www.vpngate.net/api/iphone/)에서 한국 VPN 서버만 추출하여 무작위로 연결합니다.
브라우저 프록시 설정에서 localhost:8118을 설정하여 사용할 수 있습니다.

# 시작

```bash
docker run --rm -it \
--cap-add=NET_ADMIN --device=/dev/net/tun \
--dns=1.1.1.1 --dns=8.8.8.8 --dns=9.9.9.9 \
-p 8118:8118 \
ateliersjp/kr-vpngate-proxy
```

# 시작 확인

proxy 지정 유무에 관계없이 curl하여 글로벌 IP가 다르면 성공입니다.

```bash
$ curl inet-ip.info
$ curl inet-ip.info -x http://localhost:8118
```