---
layout: post
title:  키 캡슐화 메커니즘 (Key Encapsulation Mechanism, KEM)
date:   2099-03-05 +0900
categories: security
---

## 키 캡슐화 메커니즘 (Key Encapsulation Mechanism, KEM)
> Key Encapsulation Mechanism (KEM)과 RSA 암호를 사용한 키 전송 방법의 공통점과 차이점

### 개요

키 캡슐화 메커니즘 (KEM)은 공개 채널을 통해 안전하게 공유된 비밀 키를 생성하는 암호화 프로토콜입니다. 

### 주요 특징

* **비대칭 암호화 사용:** KEM은 공개 키 암호화 알고리즘을 사용하여 비밀 키를 캡슐화합니다. 
* **공유된 비밀 키 생성:** KEM은 두 개의 서로 다른 키, 캡슐화 키 (encapsulation key)와 탈캡슐화 키 (decapsulation key)를 생성합니다. 
* **안전한 키 공유:** KEM은 공개 채널을 통해 캡슐화 키를 안전하게 전송하여 공유된 비밀 키를 생성합니다. 

### 작동 방식

KEM은 다음과 같은 3가지 단계로 작동합니다.

1. **키 생성:** 
    - 캡슐화 키 (encapsulation key)와 탈캡슐화 키 (decapsulation key)를 생성합니다. 
    - 탈캡슐화 키는 비밀로 유지하고 캡슐화 키는 공개합니다. 
2. **키 캡슐화:** 
    - 캡슐화 키를 사용하여 공유된 비밀 키를 암호화합니다. 
    - 암호화된 키 (encapsulated key)를 공개 채널을 통해 전송합니다. 
3. **키 탈캡슐화:** 
    - 탈캡슐화 키를 사용하여 암호화된 키를 암호 해독합니다. 
    - 암호 해독된 키는 공유된 비밀 키가 됩니다. 

### 장점

* **공개 채널 사용:** KEM은 공개 채널을 통해 안전하게 키를 공유할 수 있습니다. 
* **비밀 키 보호:** KEM은 탈캡슐화 키를 비밀로 유지하여 공유된 비밀 키를 보호합니다. 
* **효율성:** KEM은 비대칭 암호화 알고리즘을 사용하지만, 공유된 비밀 키는 대칭 암호화 알고리즘에 사용될 수 있어 효율성을 높입니다. 

### 단점

* **공격 가능성:** KEM은 공격자가 캡슐화 키를 가로채 공유된 비밀 키를 추출할 가능성이 있습니다. 
* **계산량:** KEM은 비대칭 암호화 알고리즘을 사용하기 때문에 계산량이 많이 필요합니다. 

### 활용 분야

* **TLS 프로토콜:** TLS 프로토콜은 서버와 클라이언트 간의 안전한 통신을 위해 KEM을 사용합니다. 
* **SSH 프로토콜:** SSH 프로토콜은 서버와 클라이언트 간의 안전한 로그인을 위해 KEM을 사용합니다. 
* **IPsec 프로토콜:** IPsec 프로토콜은 네트워크 트래픽의 안전성을 위해 KEM을 사용합니다. 

### 참고자료

* Wikipedia: Key encapsulation mechanism: [https://en.wikipedia.org/wiki/Key_encapsulation_mechanism](https://en.wikipedia.org/wiki/Key_encapsulation_mechanism)
* NIST Special Publication 800-56A: Recommendation for Pair-Wise Key Establishment Schemes Using Discrete Logarithm Cryptography: [유효하지 않은 URL 삭제됨]



## Key Encapsulation Mechanism (KEM)과 RSA 암호를 사용한 키 전송 방법의 관계

**KEM**과 **RSA 암호를 사용한 키 전송 방법**은 모두 공개 채널을 통해 안전하게 공유된 비밀 키를 생성하는 방법이지만, 서로 다른 방식으로 작동합니다.

**KEM**은 다음과 같은 특징을 가지고 있습니다.

* **비대칭 암호화 사용:** KEM은 공개 키 암호화 알고리즘을 사용하여 비밀 키를 캡슐화합니다. 
* **공유된 비밀 키 생성:** KEM은 두 개의 서로 다른 키, 캡슐화 키 (encapsulation key)와 탈캡슐화 키 (decapsulation key)를 생성합니다. 
* **안전한 키 공유:** KEM은 공개 채널을 통해 캡슐화 키를 전송하여 공유된 비밀 키를 생성합니다. 

**RSA 암호를 사용한 키 전송 방법**은 다음과 같은 특징을 가지고 있습니다.

* **비대칭 암호화 사용:** RSA 암호는 공개 키와 개인 키로 구성된 비대칭 암호화 알고리즘을 사용합니다. 
* **공유된 비밀 키 생성:** 두 개의 서로 다른 키, 공개 키 (public key)와 개인 키 (private key)를 사용하여 공유된 비밀 키를 생성합니다. 
* **안전한 키 공유:** RSA 암호는 공개 채널을 통해 공개 키를 전송하여 공유된 비밀 키를 생성합니다. 

**두 방법의 주요 차이점**은 다음과 같습니다.

* **KEM**은 공개 키 암호화 알고리즘을 사용하여 비밀 키를 캡슐화하는 반면, **RSA 암호를 사용한 키 전송 방법**은 공개 키 암호화 알고리즘을 사용하여 공유된 비밀 키를 직접 암호화합니다.
* **KEM**은 캡슐화 키와 탈캡슐화 키를 생성하는 반면, **RSA 암호를 사용한 키 전송 방법**은 공개 키와 개인 키를 생성합니다.
* **KEM**은 암호화된 키를 전송하는 반면, **RSA 암호를 사용한 키 전송 방법**은 암호화된 공유된 비밀 키를 전송합니다.

**두 방법의 관계**는 다음과 같습니다.

* **KEM**은 캡슐화 키를 암호화하는 데 RSA 암호를 사용할 수 있습니다.
* **RSA 암호를 사용한 키 전송 방법**은 KEM을 사용하여 공유된 비밀 키를 생성하는 데 사용할 수 있습니다.

**결론적으로, KEM과 RSA 암호를 사용한 키 전송 방법은 서로 다른 방식으로 작동하지만, 서로 보완적인 관계를 가지고 있습니다.**


## RSA 암호를 사용한 키 전송 요약

### 개요
RSA 암호를 사용한 키 전송은 공개 채널을 통해 안전하게 공유된 비밀 키를 생성하는 방법입니다. 
1. A는 난수 r을 만들고, B pubB로 RSA Encrypt 하여 전송
2. B는 priB로 Decrypt해서 r을 얻는다
3. A와 B는 KDF(r)을 하여 공유키 K를 얻는다 (KDF: 키 유도함수)

### 주요 특징

* **비대칭 암호화 사용:** RSA 암호는 공개 키와 개인 키로 구성된 비대칭 암호화 알고리즘을 사용합니다. 
* **공유된 비밀 키 생성:** 두 개의 서로 다른 키, 공개 키 (public key)와 개인 키 (private key)를 사용하여 공유된 비밀 키를 생성합니다. 
* **안전한 키 공유:** 공개 채널을 통해 공개 키를 전송하여 공유된 비밀 키를 생성합니다. 

### 작동 방식

RSA 암호를 사용한 키 전송은 다음과 같은 3가지 단계로 작동합니다.

1. **키 생성:** 
    - 공개 키와 개인 키를 생성합니다. 
    - 개인 키는 비밀로 유지하고 공개 키는 공개합니다. 
2. **키 암호화:** 
    - 공유된 비밀 키를 공개 키로 암호화합니다. 
    - 암호화된 키를 공개 채널을 통해 전송합니다. 
3. **키 암호 해독:** 
    - 개인 키를 사용하여 암호화된 키를 암호 해독합니다. 
    - 암호 해독된 키는 공유된 비밀 키가 됩니다. 

### 장점

* **공개 채널 사용:** RSA 암호를 사용한 키 전송은 공개 채널을 통해 안전하게 키를 공유할 수 있습니다. 
* **비밀 키 보호:** 개인 키를 비밀로 유지하여 공유된 비밀 키를 보호합니다. 
* **널리 사용:** RSA 암호는 가장 널리 사용되는 암호화 알고리즘 중 하나입니다. 

### 단점

* **공격 가능성:** RSA 암호는 공격자가 공개 키를 사용하여 공유된 비밀 키를 추출할 가능성이 있습니다. 
* **계산량:** RSA 암호는 계산량이 많이 필요합니다. 

### 활용 분야

* **TLS 프로토콜:** TLS 프로토콜은 서버와 클라이언트 간의 안전한 통신을 위해 RSA 암호를 사용한 키 전송을 사용합니다. 
* **SSH 프로토콜:** SSH 프로토콜은 서버와 클라이언트 간의 안전한 로그인을 위해 RSA 암호를 사용한 키 전송을 사용합니다. 
* **S/MIME:** S/MIME은 전자 메일의 안전성을 위해 RSA 암호를 사용한 키 전송을 사용합니다. 

### 참고자료

* Wikipedia: RSA (cryptosystem): [https://en.wikipedia.org/wiki/RSA](https://en.wikipedia.org/wiki/RSA)_\(cryptosystem\)
* NIST Special Publication 800-56B: Recommendation for Pair-Wise Key Establishment Schemes Using Discrete Logarithm Cryptography: [https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf)

