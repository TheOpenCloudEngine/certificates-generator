# TLS를 위한 인증서 생성기

* `generate_certs.sh`
  *  내부 CA를 생성하고, hosts.txt에 나열된 각 호스트에 대해 CA 서명한 인증서를 생성하는 스크립트
  * 실행시 `./generate_certs.sh` 으로 반드시 실행하도록 함

## 실행

```
# ./generate_certs.sh 
============================================================
 인증서 생성 스크립트
============================================================
 조직 정보: C=KR, ST=Gyeonggi-do, L=Yongin-si, O=Open Cloud Engine Community, OU=Platform Engineering
 도메인: opencloudengine.org
============================================================

[1/3] CA (Certificate Authority) 생성 중...
  -> 기존 CA가 존재합니다. 기존 CA를 사용합니다.
     CA 인증서: ./certs/ca/ca.crt
     (새로 생성하려면 ./certs/ca 디렉토리를 삭제 후 재실행)

[2/3] 호스트별 인증서 생성 중...

  ---- cm-server (cm-server.opencloudengine.org) ----
    [+] 개인키 생성: ./certs/cm-server/cm-server.key
    [+] CSR 생성:   ./certs/cm-server/cm-server.csr
    [+] 확장설정:   ./certs/cm-server/cm-server.ext
    [+] 인증서:     ./certs/cm-server/cm-server.crt
    [+] 체인 PEM:   ./certs/cm-server/cm-server.pem
    [+] 통합 PEM:   ./certs/cm-server/cm-server-full.pem

  ---- node01 (node01.opencloudengine.org) ----
    [+] 개인키 생성: ./certs/node01/node01.key
    [+] CSR 생성:   ./certs/node01/node01.csr
    [+] 확장설정:   ./certs/node01/node01.ext
    [+] 인증서:     ./certs/node01/node01.crt
    [+] 체인 PEM:   ./certs/node01/node01.pem
    [+] 통합 PEM:   ./certs/node01/node01-full.pem

  ---- node02 (node02.opencloudengine.org) ----
    [+] 개인키 생성: ./certs/node02/node02.key
    [+] CSR 생성:   ./certs/node02/node02.csr
    [+] 확장설정:   ./certs/node02/node02.ext
    [+] 인증서:     ./certs/node02/node02.crt
    [+] 체인 PEM:   ./certs/node02/node02.pem
    [+] 통합 PEM:   ./certs/node02/node02-full.pem

  ---- node03 (node03.opencloudengine.org) ----
    [+] 개인키 생성: ./certs/node03/node03.key
    [+] CSR 생성:   ./certs/node03/node03.csr
    [+] 확장설정:   ./certs/node03/node03.ext
    [+] 인증서:     ./certs/node03/node03.crt
    [+] 체인 PEM:   ./certs/node03/node03.pem
    [+] 통합 PEM:   ./certs/node03/node03-full.pem

[3/3] 인증서 검증 중...

  ---- cm-server ----
    [OK] CA 서명 검증 통과
    [인증서] 인증서정보 출력
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 31 (0x1f)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = KR, ST = Gyeonggi-do, L = Seongnam-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = Open Cloud Engine Community CA
        Validity
            Not Before: Mar 13 02:06:23 2026 GMT
            Not After : Jun 15 02:06:23 2028 GMT
        Subject: C = KR, ST = Gyeonggi-do, L = Yongin-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = cm-server.opencloudengine.org
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:cb:50:43:62:1c:b1:a4:6f:59:20:38:07:37:26:
                    6a:6b:10:6b:d6:4c:71:cb:04:96:c9:90:b6:90:ec:
                    f5:79:85:f2:6e:06:96:65:6c:4b:05:25:dc:78:fe:
                    c2:b5:cf:09:77:38:63:fc:cd:e9:a0:ed:98:9f:27:
                    2e:61:ad:4c:55:cf:1e:31:d1:d7:39:33:86:e0:dc:
                    7c:cc:f6:e1:65:80:c6:1a:18:62:d7:4f:0d:e6:e2:
                    3e:3a:68:3c:38:c0:a8:33:4f:8a:33:de:36:e4:9e:
                    56:49:e1:36:68:25:28:58:47:01:f9:b8:f4:ff:9e:
                    5b:08:a9:ba:79:8a:1b:2b:a8:f1:bc:bf:cd:d4:eb:
                    c3:43:f4:6f:06:2a:54:96:85:74:11:ca:25:fb:9c:
                    db:e1:7b:de:a9:fc:a6:97:76:21:15:8e:4f:31:57:
                    24:88:78:22:f3:0f:8a:db:6e:a1:22:68:7b:96:ee:
                    bd:28:64:03:7f:80:39:74:2c:83:85:c3:ff:af:90:
                    57:71:60:ea:8e:61:3e:92:15:cb:13:b5:66:24:ba:
                    36:e2:58:9f:3d:2f:5c:4f:1c:5d:41:b8:5d:74:5f:
                    ba:c7:41:c5:ab:d4:2f:41:c1:fb:64:11:e1:42:f3:
                    fa:c8:14:e7:62:a3:5f:eb:d0:01:ad:00:4e:90:03:
                    cb:07
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Authority Key Identifier: 
                86:36:7D:64:6A:77:E7:D9:98:21:AE:88:2E:2B:08:BF:B2:60:03:81
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Key Usage: critical
                Digital Signature, Key Encipherment
            X509v3 Extended Key Usage: 
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 Subject Alternative Name: 
                DNS:cm-server.opencloudengine.org, DNS:cm-server, DNS:*.opencloudengine.org
            X509v3 Subject Key Identifier: 
                77:9F:32:12:30:68:D7:68:49:AA:D4:9E:10:C0:B3:2A:DC:BA:23:3E
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        01:2d:b2:99:0c:6e:7e:0e:7a:55:43:52:84:49:b7:a3:da:cf:
        a9:68:dd:3b:38:e2:cc:c8:1e:ab:a8:1d:8d:24:cb:ab:1d:7e:
        e6:b5:da:66:b4:6f:b5:87:db:29:08:3b:8b:c9:1f:66:cc:c8:
        a7:36:53:57:26:fa:da:36:f8:39:d6:18:d9:54:9c:07:a7:07:
        86:3a:5c:45:fd:fc:f2:3c:7e:09:87:5a:f4:14:6a:b4:5c:68:
        a9:53:90:c0:4e:f3:10:0c:3a:59:25:9e:3a:33:e9:34:30:03:
        b2:40:a3:39:96:88:7a:4e:e8:d7:fc:eb:8f:71:0e:bc:4b:29:
        0a:18:9c:30:5c:7a:a8:ec:09:e7:b5:26:29:8c:41:90:69:6c:
        a8:58:63:2c:3f:f3:0d:c7:61:9e:41:77:9a:57:3c:1d:3b:e3:
        18:84:3e:bf:1a:e0:35:43:93:05:cf:21:80:32:7c:1e:46:80:
        e5:c8:44:b2:5a:1d:1d:6a:90:2b:21:8b:84:dc:99:f6:fa:f7:
        b8:8a:8f:f8:fa:09:5c:d1:af:0b:4f:24:27:31:8b:a3:5c:f2:
        f6:7c:a2:ab:f6:eb:5a:d3:9f:75:86:8d:8c:0f:c5:3b:74:2d:
        6e:b7:51:5e:59:09:1a:18:a2:a5:1f:7c:e4:77:ef:2b:c3:5f:
        5b:0e:b9:64:d0:6a:1d:51:cd:38:76:30:ae:14:5f:d8:fb:01:
        60:a1:eb:ce:43:39:61:90:d5:8e:c6:97:7d:d1:87:80:36:68:
        a0:98:e0:e6:e8:45:89:9f:db:e3:88:55:02:fa:b3:d5:59:c0:
        30:a1:e0:b1:8b:df:e5:60:63:ce:29:53:f7:47:46:24:1e:2b:
        9d:1b:23:b6:d2:ed:2a:62:78:d2:04:f8:d8:de:86:b3:4a:15:
        9a:8e:56:77:f8:da:11:71:d6:aa:b8:c4:1a:91:a4:cd:81:b5:
        48:77:82:73:c4:c7:2f:b4:54:48:8d:9f:23:02:24:b7:1b:ef:
        2d:07:5c:2e:17:56:3e:78:97:7c:33:ba:87:80:3e:ea:4e:85:
        20:54:73:aa:0b:2c:64:a5:5e:fa:18:71:32:91:4b:64:92:1c:
        55:f7:72:81:a0:23:79:78:a4:0a:06:fa:c6:e5:26:21:4a:29:
        bb:d1:51:c7:af:90:50:80:79:08:a0:9d:af:8e:fe:87:5a:97:
        ce:24:eb:7b:e2:ff:90:70:80:6c:81:f3:15:7c:22:53:00:ad:
        6f:18:2c:34:e7:2a:7b:74:0a:e7:38:a8:d6:38:9d:56:c5:cc:
        c5:2e:59:72:d7:20:89:08:3f:21:30:82:6f:05:11:54:81:23:
        59:79:00:ad:cb:4d:22:b9
    [OK] Extended Key Usage: Server + Client Auth
    [OK] SAN: DNS:cm-server.opencloudengine.org

  ---- node01 ----
    [OK] CA 서명 검증 통과
    [인증서] 인증서정보 출력
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 32 (0x20)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = KR, ST = Gyeonggi-do, L = Seongnam-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = Open Cloud Engine Community CA
        Validity
            Not Before: Mar 13 02:06:24 2026 GMT
            Not After : Jun 15 02:06:24 2028 GMT
        Subject: C = KR, ST = Gyeonggi-do, L = Yongin-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = node01.opencloudengine.org
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:aa:20:3a:88:d8:fc:0f:11:b1:81:03:ab:f3:74:
                    95:97:9b:ca:5d:96:8a:01:d7:8a:75:e4:e2:67:1d:
                    b2:9a:15:28:02:b2:0e:9d:4b:67:d2:92:eb:57:96:
                    8d:36:53:d0:b4:6b:d5:78:a4:cb:e9:58:20:9c:43:
                    90:5d:6b:e6:74:7a:c9:9c:5a:97:86:0c:d0:be:b1:
                    f5:27:72:3b:01:60:79:b4:a2:58:4e:d7:f3:6b:c4:
                    c4:9d:d6:47:db:f2:61:27:55:66:98:8b:aa:d8:f9:
                    eb:81:ae:7b:59:f0:e3:1b:81:c4:f9:e1:0a:fb:f4:
                    5f:bf:63:c4:c5:83:76:0a:f6:de:2e:79:3b:f7:8c:
                    c2:df:e1:5c:0f:d1:b2:82:a1:30:ad:0f:ba:09:6d:
                    73:e4:08:6f:1e:dc:8e:6e:ab:63:dd:ab:8f:ab:40:
                    50:a2:74:20:ca:51:23:44:0d:c8:e7:28:75:17:59:
                    48:37:d3:a5:17:41:ff:6e:a8:24:53:f5:6b:57:80:
                    8a:a6:9e:9e:71:e5:c9:fb:f4:22:63:16:5d:4e:12:
                    97:89:b1:2e:a9:28:64:35:28:43:a1:ee:b4:ff:36:
                    7f:00:18:83:78:4c:2f:1b:27:ac:c1:fe:1c:50:84:
                    c6:77:74:8b:76:7b:13:23:31:e4:ad:10:26:fb:0d:
                    76:df
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Authority Key Identifier: 
                86:36:7D:64:6A:77:E7:D9:98:21:AE:88:2E:2B:08:BF:B2:60:03:81
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Key Usage: critical
                Digital Signature, Key Encipherment
            X509v3 Extended Key Usage: 
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 Subject Alternative Name: 
                DNS:node01.opencloudengine.org, DNS:node01, DNS:*.opencloudengine.org
            X509v3 Subject Key Identifier: 
                5E:D5:64:A4:25:A3:01:21:31:7D:84:D4:B7:9B:A3:73:D8:B5:B5:3A
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        2c:61:00:bf:ec:fa:87:02:fd:e7:5c:1f:2d:2b:92:64:c0:2f:
        0e:80:5e:17:01:d7:28:4e:1c:a2:2a:e4:65:2b:d7:2c:0c:25:
        ad:d5:f1:06:5f:a9:1d:a2:a6:99:ac:01:65:84:ba:11:19:25:
        60:30:a0:5b:e9:cc:a6:e9:e4:06:87:c4:6a:df:1f:8f:eb:ed:
        67:8e:18:62:83:24:5e:cc:e8:9b:be:03:4a:ac:68:a3:f5:d7:
        ac:34:30:34:c4:e0:e3:f9:2a:c1:74:a0:7e:38:09:61:b7:94:
        38:aa:55:b8:1a:c3:ba:94:1a:a9:51:88:3e:70:50:6f:4c:f6:
        d8:d1:a1:77:fa:9f:76:5b:8e:25:a9:df:0d:04:9a:29:9d:b4:
        ca:0a:83:3c:b8:a5:33:5f:35:e6:dd:cb:23:65:f5:2c:ac:88:
        c7:60:af:e1:c3:0f:43:0f:dd:02:7f:a3:4a:63:2d:bb:6f:67:
        f4:90:93:96:3c:da:f4:13:a2:69:96:36:66:4c:71:85:d8:c4:
        f7:05:8b:9e:29:7d:e1:35:8b:19:27:2c:72:02:d8:3f:9a:05:
        cd:1e:13:7a:f0:ce:d7:bf:a1:b5:0d:f0:42:58:26:ac:9f:9d:
        6f:ad:41:c2:f2:fb:1c:e6:9f:71:df:de:f9:b9:eb:a3:40:8b:
        d9:6a:2e:c1:4b:a6:43:d3:03:17:48:6d:65:19:f8:10:29:9f:
        73:d1:25:0e:92:6b:08:1d:18:81:8b:85:cc:8b:8a:ba:f2:41:
        5d:54:8f:fc:69:a8:5b:16:c5:1f:54:4d:e0:c8:74:9b:16:30:
        45:f0:a7:21:79:db:8b:26:be:6e:fa:16:24:16:3a:a1:2b:82:
        01:64:4f:b5:12:75:08:11:68:c2:52:e3:8e:ae:fd:e1:d1:89:
        20:61:4b:47:28:0d:25:24:3f:3c:9f:d5:51:1d:76:0e:a4:12:
        bf:ab:97:28:dd:0f:7e:4d:5a:0d:77:c5:74:a1:ad:7e:fe:2a:
        bc:45:a4:7e:56:ff:c3:82:b7:50:23:c9:1c:83:37:4d:a0:41:
        27:54:71:24:28:72:fa:d6:9d:9e:dc:53:bf:3f:21:0f:86:c5:
        27:cd:4b:d4:d1:c7:71:e2:5f:05:b4:e2:3b:62:5c:71:f4:b3:
        83:f4:9f:42:b2:8f:0c:da:d9:08:c2:1f:1a:ae:52:a4:03:98:
        09:6b:f3:fc:ff:08:36:ce:bf:6e:42:5c:ba:fe:12:54:23:ee:
        e3:3d:77:f0:e3:63:df:1a:d3:d2:c6:90:b0:1c:61:a5:30:88:
        5f:f9:0a:1f:02:5e:4a:36:0b:aa:d2:54:f3:73:ae:52:65:55:
        17:19:62:a7:de:e1:52:9e
    [OK] Extended Key Usage: Server + Client Auth
    [OK] SAN: DNS:node01.opencloudengine.org

  ---- node02 ----
    [OK] CA 서명 검증 통과
    [인증서] 인증서정보 출력
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 33 (0x21)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = KR, ST = Gyeonggi-do, L = Seongnam-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = Open Cloud Engine Community CA
        Validity
            Not Before: Mar 13 02:06:24 2026 GMT
            Not After : Jun 15 02:06:24 2028 GMT
        Subject: C = KR, ST = Gyeonggi-do, L = Yongin-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = node02.opencloudengine.org
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:9f:0f:0e:50:ac:d0:94:bd:84:0f:11:c1:b4:a7:
                    b7:6a:ae:8f:e0:ea:61:97:82:c0:c6:ea:45:d1:90:
                    43:5f:9d:5a:de:49:7e:b0:65:84:fa:df:21:8c:6b:
                    ad:91:87:6a:9a:f0:14:b0:5f:c2:32:15:0c:08:65:
                    23:9e:d2:5d:33:9b:a2:7b:5b:03:40:c5:b4:94:9c:
                    3f:0a:be:4e:0d:a1:18:b8:45:15:ad:e5:91:fd:28:
                    d2:82:95:d6:fd:92:67:36:7b:c6:ce:f3:88:ed:70:
                    c6:a3:14:97:73:97:d4:37:69:8e:90:cd:61:a7:a8:
                    64:34:53:bc:06:3d:e8:3d:06:4d:32:f9:cd:5c:fd:
                    39:bd:10:4d:14:82:71:42:fd:c6:ca:8a:71:79:0d:
                    65:2c:ec:4e:78:90:d6:bf:09:91:66:ea:6b:32:5b:
                    0e:06:5f:58:6f:61:a3:cc:7a:29:f1:2e:ff:63:1b:
                    2a:ed:ff:f3:1c:63:8b:ce:fc:25:9a:97:67:8a:60:
                    7e:09:ce:6c:0b:be:f3:f9:12:b7:bb:7c:82:ab:f5:
                    db:4f:f7:ec:e3:83:32:71:a3:5a:22:d8:c5:03:50:
                    11:a5:09:a9:a5:6d:61:74:00:18:75:4e:3d:c3:0c:
                    7e:00:35:79:1d:82:2f:dd:d8:11:75:20:84:07:d9:
                    c1:95
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Authority Key Identifier: 
                86:36:7D:64:6A:77:E7:D9:98:21:AE:88:2E:2B:08:BF:B2:60:03:81
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Key Usage: critical
                Digital Signature, Key Encipherment
            X509v3 Extended Key Usage: 
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 Subject Alternative Name: 
                DNS:node02.opencloudengine.org, DNS:node02, DNS:*.opencloudengine.org
            X509v3 Subject Key Identifier: 
                CA:62:85:C2:97:A2:16:A3:3D:3C:AD:83:5D:7A:66:D5:FF:72:14:9C
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        06:f8:96:be:db:cb:8a:10:1c:88:26:92:59:67:ce:78:a0:76:
        08:16:10:43:16:f6:e8:10:9d:a6:b1:d8:a2:27:5f:98:72:07:
        34:c8:0c:e1:04:73:45:b2:9e:b3:9b:2d:24:b9:22:24:e0:1a:
        db:64:9b:cd:71:b7:97:b0:2f:c0:79:2d:13:87:9a:d4:4e:1a:
        6c:71:1b:31:90:a1:da:7c:a0:83:89:af:8e:45:e8:34:53:6f:
        e1:7a:ea:90:2b:87:97:f6:75:ff:59:71:9a:9c:fd:4c:66:33:
        5a:19:81:0e:4f:77:da:6d:a2:c9:be:7c:ad:b4:e8:d4:10:9d:
        9d:52:6f:f9:4b:18:97:60:34:b8:be:a4:83:cd:25:67:4e:3f:
        b6:7b:35:e8:d5:f0:45:bd:0b:82:9d:01:aa:18:20:62:c5:ff:
        64:bb:ea:09:f8:e6:09:e7:ae:f0:98:54:17:e1:b5:6e:94:22:
        83:78:34:c7:4b:58:d2:31:70:1a:00:f0:1a:cd:a3:29:21:b8:
        2f:55:e0:d5:e2:48:69:a6:09:16:bb:74:e0:fd:31:87:cf:b0:
        21:d6:d3:9e:74:74:c2:8e:31:65:c1:3d:a2:3d:5c:20:b9:7d:
        05:68:43:8a:eb:02:d2:81:8d:e0:ed:d5:f9:18:ff:3f:c1:c6:
        a2:6c:2b:59:79:fa:b3:87:00:22:0e:0e:64:7a:5b:25:a1:0e:
        4b:88:ca:d5:46:55:c9:f8:ed:7a:91:e3:11:09:06:09:86:37:
        ee:4b:bb:3e:63:ad:76:cf:05:aa:b4:4a:af:c7:5b:3f:48:e8:
        ee:dc:ef:34:18:17:9e:7d:cb:57:52:ea:af:8b:36:00:4f:32:
        2b:2a:ec:55:ff:76:bd:26:4d:7c:99:16:e2:69:c1:56:f8:63:
        cb:c4:35:49:2d:a0:c9:69:25:6c:fc:9b:88:23:1d:6e:53:a0:
        aa:9f:d8:d4:41:d3:f5:5b:70:fa:d6:c0:9c:73:99:02:b0:8e:
        e8:8c:98:5f:c9:54:0c:2b:f6:c9:f3:51:91:cc:3a:9f:a7:22:
        86:46:10:96:b6:b7:05:53:28:ec:dc:7a:bc:11:09:1e:34:33:
        ad:15:ad:0a:00:b7:fc:c2:55:2a:eb:7f:27:8f:d6:b3:9c:2d:
        ba:a8:31:0a:67:2c:c0:3c:c4:8d:ba:4d:2b:9d:f6:0b:7b:d4:
        ff:c8:88:59:f8:c6:32:6b:6d:72:e6:39:96:04:c5:db:4b:d4:
        e9:12:c7:42:19:64:c2:04:ad:20:9e:8d:6d:61:89:90:cb:a5:
        d6:77:1b:d4:83:bc:42:d8:bf:1a:6e:f4:c9:9c:ea:25:c4:b5:
        a0:39:bb:af:bd:2e:cb:db
    [OK] Extended Key Usage: Server + Client Auth
    [OK] SAN: DNS:node02.opencloudengine.org

  ---- node03 ----
    [OK] CA 서명 검증 통과
    [인증서] 인증서정보 출력
Certificate:
    Data:
        Version: 3 (0x2)
        Serial Number: 34 (0x22)
        Signature Algorithm: sha256WithRSAEncryption
        Issuer: C = KR, ST = Gyeonggi-do, L = Seongnam-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = Open Cloud Engine Community CA
        Validity
            Not Before: Mar 13 02:06:24 2026 GMT
            Not After : Jun 15 02:06:24 2028 GMT
        Subject: C = KR, ST = Gyeonggi-do, L = Yongin-si, O = Open Cloud Engine Community, OU = Platform Engineering, CN = node03.opencloudengine.org
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:d8:ab:c0:c9:4e:5f:d2:07:66:fe:a1:00:6c:ad:
                    27:f7:7c:2f:da:53:f6:52:bf:e6:51:95:03:2b:ea:
                    01:20:53:05:1b:40:60:5d:07:14:89:e0:1c:89:fb:
                    d0:72:e0:e6:41:1a:85:79:ed:f5:7b:41:83:c5:6f:
                    00:93:41:25:3b:df:34:72:5e:74:35:b7:70:2d:fa:
                    2f:a1:c1:9c:31:2b:42:ff:39:ee:08:a6:2d:ae:48:
                    3a:f8:4d:53:44:4b:f1:89:a5:77:bc:22:53:00:98:
                    c1:e3:02:a1:20:39:fa:83:a3:32:4d:c5:af:3b:a9:
                    40:a2:93:8a:48:4c:64:88:17:d5:c7:2c:d1:cb:61:
                    27:62:4f:24:a1:7f:5c:c3:db:e5:d1:cf:c3:66:25:
                    0e:2f:c0:bb:2c:d0:e3:a3:ea:7e:94:d1:0f:a9:ef:
                    48:0b:7c:60:01:13:a9:32:1a:40:15:99:59:99:99:
                    80:a3:1d:ec:58:47:5f:39:05:db:c7:83:fe:b1:fc:
                    09:e4:8e:04:d5:b3:74:ac:2a:92:3c:49:da:32:16:
                    b4:b9:63:b3:e1:ea:81:e2:34:b0:e4:74:c3:df:2d:
                    58:6b:c1:16:57:5e:c9:f7:ee:fc:ad:28:09:1a:1a:
                    81:7b:03:95:e9:64:d1:32:aa:b5:97:65:9f:5f:52:
                    d7:ed
                Exponent: 65537 (0x10001)
        X509v3 extensions:
            X509v3 Authority Key Identifier: 
                86:36:7D:64:6A:77:E7:D9:98:21:AE:88:2E:2B:08:BF:B2:60:03:81
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Key Usage: critical
                Digital Signature, Key Encipherment
            X509v3 Extended Key Usage: 
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 Subject Alternative Name: 
                DNS:node03.opencloudengine.org, DNS:node03, DNS:*.opencloudengine.org
            X509v3 Subject Key Identifier: 
                0A:2B:80:A0:33:B3:83:F4:86:D8:E1:A8:17:DF:E9:20:E4:CB:24:FA
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        83:62:bd:f4:d8:22:77:c2:47:e2:d5:ba:47:36:db:22:fc:3a:
        c5:76:75:7b:90:65:fc:e4:fb:a7:59:dc:9d:d2:3c:aa:cc:53:
        6b:54:aa:7a:a4:e3:65:68:96:7c:9b:f4:a0:a6:15:b4:75:3f:
        b9:f4:0c:5a:4f:e4:3a:4e:1a:31:08:9f:c3:59:7d:e7:23:c7:
        d7:5f:d1:4f:fe:f7:aa:30:1f:cb:fc:ac:e0:1d:3b:26:cb:77:
        8a:e9:e4:be:22:29:c9:28:41:5a:f6:b4:39:2a:20:32:3b:d4:
        ea:d8:0f:cd:74:9b:94:f6:81:a1:65:65:80:ec:59:da:31:db:
        ed:09:f1:58:5c:bc:2d:4b:01:2f:e8:72:ce:17:ad:d5:19:83:
        53:08:6f:f4:21:85:7e:c5:f3:9d:a1:7f:20:70:4d:cf:a3:cd:
        c1:b6:9c:87:6b:93:39:ab:c8:f3:91:1b:7d:8d:10:72:76:7d:
        9a:da:65:8e:99:c6:e0:76:84:b5:63:16:1e:93:e5:16:07:e8:
        1b:0f:00:d1:b1:91:39:81:99:1a:68:fb:17:8d:ed:14:2e:db:
        df:5e:8b:3b:58:e7:c4:0b:9f:fb:fe:d0:30:d3:39:28:d9:a4:
        02:0b:02:2c:c1:51:ab:73:47:af:16:0a:1c:82:1c:e6:20:00:
        6b:61:0c:54:b6:68:05:50:7a:fe:f7:f1:c2:b1:16:d1:b1:45:
        08:a4:d4:43:74:f7:d4:00:04:b7:09:ed:28:80:7c:ad:5f:1e:
        e1:68:4e:15:89:c4:41:12:a5:8a:35:40:76:18:ea:69:3e:46:
        be:86:bc:a8:11:2c:fd:d4:41:13:fe:4f:85:8b:53:27:46:5a:
        10:c5:af:1c:4f:12:b0:2c:d8:6a:41:08:7a:a3:6d:3c:89:0a:
        6c:f9:e9:02:ed:e8:30:3e:96:89:f3:cc:0e:bc:61:0b:2a:f6:
        9b:97:ed:ae:ac:36:33:4a:b9:d5:93:5b:f1:e0:4d:b6:fd:30:
        33:e6:7c:2c:34:63:ee:9c:04:fb:e4:a9:69:13:53:7d:00:69:
        1d:b9:4e:ec:cf:5d:5c:f1:0b:4f:d6:1e:26:9f:2b:d9:57:3e:
        4f:e5:05:5d:3b:ae:c0:e6:7e:e9:3a:2a:f6:fe:43:89:a8:eb:
        af:69:a1:15:54:d0:07:02:95:35:a5:e4:c4:b7:54:78:ca:62:
        f5:7f:93:4d:23:72:8b:01:dd:41:5b:5f:fa:b5:ce:56:ba:a7:
        fd:52:31:9a:42:b4:58:2c:48:16:18:a6:82:91:9e:af:e5:c0:
        ac:f8:45:b0:b2:e0:2f:34:37:f2:d4:0f:e2:ee:25:7f:fe:fe:
        62:e3:06:9e:ae:8a:1a:3c
    [OK] Extended Key Usage: Server + Client Auth
    [OK] SAN: DNS:node03.opencloudengine.org

============================================================
 완료 요약
============================================================

 출력 디렉토리 구조:
   ./certs/
   ├── ca/
   │   ├── ca.key          (CA 개인키 - 안전하게 보관)
   │   └── ca.crt          (CA 인증서 - 클라이언트에 배포)
   ├── cm-server/
   │   ├── cm-server.key     (서버 개인키)
   │   ├── cm-server.crt     (서버 인증서)
   │   ├── cm-server.pem     (인증서 체인: 서버+CA)
   │   └── cm-server-full.pem(키+체인 통합)
   ├── node01/
   │   ├── node01.key     (서버 개인키)
   │   ├── node01.crt     (서버 인증서)
   │   ├── node01.pem     (인증서 체인: 서버+CA)
   │   └── node01-full.pem(키+체인 통합)
   ├── node02/
   │   ├── node02.key     (서버 개인키)
   │   ├── node02.crt     (서버 인증서)
   │   ├── node02.pem     (인증서 체인: 서버+CA)
   │   └── node02-full.pem(키+체인 통합)
   ├── node03/
   │   ├── node03.key     (서버 개인키)
   │   ├── node03.crt     (서버 인증서)
   │   ├── node03.pem     (인증서 체인: 서버+CA)
   │   └── node03-full.pem(키+체인 통합)

 검증 결과: 4개 호스트 처리, 0개 오류

============================================================
 브라우저에서 에러 없이 사용하기 위한 안내
============================================================

 1. CA 인증서를 클라이언트(브라우저)에 신뢰 CA로 등록:
    - Windows: ca.crt 더블클릭 → '신뢰할 수 있는 루트 인증 기관'에 설치
    - macOS:   '키체인 접근' → ca.crt 가져오기 → '항상 신뢰'로 변경
    - Linux:   sudo cp ca.crt /usr/local/share/ca-certificates/
               sudo update-ca-certificates

 2. 웹 서버 설정 예시 (Nginx):
    ssl_certificate     /path/to/<host>.pem;    # 체인 인증서
    ssl_certificate_key /path/to/<host>.key;    # 개인키

 3. Java 환경:
    - JKS 변환: openssl pkcs12 → keytool importkeystore
    - CA를 JDK truststore(jssecacerts)에 등록 : keytool -importcert -alias opencloudengine.org -file ./certs/ca/ca.crt -keystore <JAVA_HOME>/lib/security/cacerts -storepass changeit
```

실행후 디렉토리 및 파일의 구조는 다음과 같습니다.

```
.
├── LICENSE
├── README.md
├── certs
│   ├── ca
│   │   ├── ca.crt
│   │   ├── ca.key
│   │   └── ca.srl
│   ├── cm-server
│   │   ├── cm-server-full.pem
│   │   ├── cm-server.crt
│   │   ├── cm-server.csr
│   │   ├── cm-server.ext
│   │   ├── cm-server.key
│   │   └── cm-server.pem
│   ├── node01
│   │   ├── node01-full.pem
│   │   ├── node01.crt
│   │   ├── node01.csr
│   │   ├── node01.ext
│   │   ├── node01.key
│   │   └── node01.pem
│   ├── node02
│   │   ├── node02-full.pem
│   │   ├── node02.crt
│   │   ├── node02.csr
│   │   ├── node02.ext
│   │   ├── node02.key
│   │   └── node02.pem
│   └── node03
│       ├── node03-full.pem
│       ├── node03.crt
│       ├── node03.csr
│       ├── node03.ext
│       ├── node03.key
│       └── node03.pem
├── generate_certs.sh
└── hosts.txt
```
