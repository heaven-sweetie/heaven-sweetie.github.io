---
layout: post
title:  "Alamofire / Swift3"
date:   2016-09-09 18:00:00 +1000
categories: [iOS]
tags: [ios, swift, alamofire, network, xcode, version, xcode-select]


---

Alamofire...

iOS app에서 Network 통신 관련 기능을 구현 때 거의 de facto의 성격이 강한 AFNetworking의 Swift 버전.

Cathage로 Alamofire를 build하려면 현재는 Swift 2.2 / Alamofire 3.5 로 build가 된다.

하지만 지금 진행하고 있는 토이 프로젝트가 Swift 3.0을 기준으로 작성중이어서 Alamofire의 Swift 3.0으로 build가 되어야 하는 상황.

현재 Alamofire의 github 페이지를 확인해보면 master branch에는 Swift 3.0지원이 적용되어 있는걸 확인할 수 있다. (release된 3.5 버전에는 아직 안되어 있는 듯 하다.)

일단 현재 Xcode의 stable 버전인 7.3.1은 Swift 2.2까지만 지원하는 상황. 그러니 GM 버전을 다운 받아야 한다. (GM 버전을 다운로드하면 프로그램명이 Xcode로 되어있는데 stable 버전과 함께 유지해야 하는 상황이라 `Xcode-beta.app`으로 GM 버전의 프로그램의 이름을 변경했다.)

그리고 Carthage로 build를 할 때 현재 기본으로 선택되어 있는 Xcode로 build를 하기 때문에 콘솔에서 선택된 Xcode의 버전을 변경해주어야 한다.

`$ sudo xcode-select -s /Applications/Xcode-beta.app/`

그리고 github의 Alamofire repository에서 master branch의 코드로 가져오기 위한 **Cartfile**을 작성한다.

`github "Alamofire/Alamofire" "master"`

그리고 `$ carthage update Alamofire --platform iOS` 으로 build를 하면 끝.