---
layout: post
title:  "kakadu 1.0 후기"
date:   2016-11-20 15:00:00 +1100
categories: [힐링캠프]
tags: [ios, swift, realm, kakadu, project, todo, tdd, unit test]
---

## 시작하기

몇년째 함께하고 있는 힐링캠프(또는 수요모임) 모임이 있다.
1주일이 한번(보통 수요일) 모여서 각자 할일을 하면서 근황토크(그냥 이런저런 사는 이야기)를 하는 모임이다.
가끔 모두의 의견이 맞으면 함께 한가지 일을 진행하곤 했다.
그러던 중 TDD 책을 공부하는데 책만 봐서는 손에 잘 익혀지지도 않고 남는게 별로 없을 것 같아 책을 보면서 책의 내용을 바탕으로 작은 앱을 만들어보게 됐다.

## 이름짓기

본격적으로 프로젝트를 시작하기위한 모임(물론 그 때 멤버 중 한명은 호주에 있어서 행아웃으로 참여했다.) 을 했을 때의 카페의 이름으로 정했다.
뭔가 [선데이토즈](http://corp.sundaytoz.com)같은 그런 느낌으로 재밌을 것 같아서 그렇게 정했다.
그런데 나중에 알고보니 호주에 있는 국립 공원이 이름!
(모임 멤버 중 절반은 호주에 있는데 인연인가 싶었다.)

## 하기

책을 각자 읽고 파트를 나눠서 작업했고 그 내용의 리뷰는 일주일에 한번씩 모여서 진행했다.
멜번에 함께하는 멤버가 있기도 했고 개인적으로 진행하는 중간에 멜번을 가게되어 오프라인 모임 + 행아웃으로 리뷰를 진행하게 됐다.

## 모이기

앞에서도 이야기했듯이 멤버의 절반이 호주에 있다보니 모든 모임을 원격으로 하게됐다.
모임의 시간상 호주에서는 카페를 갈 수 없어서 각자 집에서 참여하고 한국에서는 보통 카페에서 만나서 행아웃으로 진행했다.
각자 시간될 때 작업하고 remote branch에 push해 둔 후 그 내용을 보고 모임에서 개선할 점이라던가 다음 할일들을 이야기했다.
중요한건 그렇게 이야기된 내용들(언제까지 어떤일을 누가 진행할 건지)을 모두 기록했다는 것이다.

## 되돌아보기

일단, 가장 크게 남는 건 **결과물을 냈다는 것**.
여러 스터디나 개인 프로젝트를 하면서 결과물을 내지 못한게 너무 많았는데 이번엔 끝까지 진행해서 결과물을 스토어에서 만날 수 있게 됐다는 것이다.
굉장히 작고 어떻게보면 시작하는 사람들을 위한 튜토리얼에서나 볼 법한 정도의 앱이지만 그 안에 공부하던 TDD도 담겨있어서 더욱 의미가 있다.

다음으로는 **원격으로 프로젝트를 진행**한 경험.
일주일에 한번 정도의 모임을 제외하고는 각 개인이 시간, 장소 등을 관리했다.
물론 프로젝트가 작고 돈을 버는 일이 아니어서 가능했던 것도 있지만 추후에 프로젝트가 커진다거나 수입을 고려하며 하게될 때도 적용할만한 것들이 있다.
진행과 관련된 내용을 거의 모두 기록(커밋로그와 이슈트랙커)했고 그 기록을 바탕으로 모임을 진행하니까 일주일의 한번 정도의 모임만으로도 충분했다.

물론 아쉬운 점이 없었던 건 아니다.
처음부터 Unit Test 먼저 작성하고 해당 기능을 구현했는데 막바지에 실제로 앱을 구동하여 테스트하면서 생각하지 못했던 문제가 발생했다.
**예상하지 못한 Test**가 있었던 것이다.
일단 급한 마음에 Unit Test를 먼저 작성한다는 원칙을 깨고 바로 코드를 수정하고 수동으로 확인하고 공유했다.
앱의 구현을 모두 마친 후에 부족한 Test를 채워놓긴 했지만 어떤 부분을 놓쳤는지 다시 확인해 두고 다음에는 빼먹지 않도록 잘 챙겨야겠다.

