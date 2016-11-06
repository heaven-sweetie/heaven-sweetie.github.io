---
layout: post
title:  "Keychain / SecItemAdd returns the following error code: -34018"
date:   2016-09-04 16:00:00 +1000
categories: [iOS]
tags: [ios, swift, keychain, error]

---

Keychain Wrapper를 구현하고 싶었지만 일단 기능의 진행을 위해 다른 사람들이 구현해놓은 Wrapper를 가져다 쓰기로 했다.

그리고 간단하게 Keychain에 저장 후에 가져오는 Unit Test를 작성했는데 결과는 -34018.

저장이 안된걸 봐서는 오류가 발생한 것은 맞는데 저 Code의 의미를 알 수 없었다.

그래서 검색하다가 알게된 것.

Unit Test Target과 구현체가 있는 Target에서 하나의 Keychain을 사용하기 위해서는 Keychain Sharing 사용해야 한다는 것.

Application Tartget에서 Capabillities 항목 중 Keychain Sharing을 활성화 한 후 정상 동작하는 것을 확인 할 수 있었다.

