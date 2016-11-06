---
layout: post
title:  "github page에 글 쓰고 twitter에 알리기(1)"
date:   2016-10-25 13:00:00 +1100
categories: [twitter]
tags: [twitter, github]

---



얼마전 [멜번으로 오기 전 준비한/할 것](http://heaven-sweetie.github.io/melbourne/australia/workingholiday/2016/10/23/prepare-for-go-melbourne.html) 이라는 글을 쓰고 주변에 몇몇분에게 읽어봐달라고 부탁했었다.

그러다 블로깅을 하면 트윗을 써서 알리라고 혼났다… (음_!?)

그럼 어떻게 깃헙 페이지로 글을 쓰고 깃헙에 올렸을 때 트위터에 알리는 방법에 대해 알아보자.



# 1. github integration



자신의 github page 의 github repository 로 가서 "Setting" 항목에 가보면 "Integrations & services"라는 항목을 선택한다.

![take 1](https://c2.staticflickr.com/6/5778/29900470103_0705ef0b65_o.png)

다음에 나오는 페이지에서 "Services" 항목 오른쪽에 "Add service"를 선택하면 intergration이 가능한 다양한 서비스 목록을 볼 수 있다. 그 중에서 twitter를 선택한다. (물론 너무 많은 서비스가 나오니 검색을 하도록 하자.)

![take 2](https://c2.staticflickr.com/6/5600/30533204935_754a534816_o.png)

다음으로 twitter의 OAuth를 활용하기 위한 정보를 입력하는 페이지가 나오는데 "Install Notes" 첫번째 항목인 "Get an OAuth Token for Your Twitter Account."을 선택하면 자동으로 twitter의 인증페이지로 연결해서 "Token"과 "Secret" 값을 가져온다.

![take 3](https://c2.staticflickr.com/6/5566/30533204715_2ec0d981d6_o.png)

![take 4](https://c2.staticflickr.com/6/5561/30446000261_53e8ec6b49_o.png)

![take 5](https://c2.staticflickr.com/6/5516/30533204475_6d46ce1fb4_o.png)

마지막으로 "Add service" 또는 "Update service"를 선택하면 연결이 끝난다.

"Digest"나 "Short format"을 선택하지 않으면 github page의 링크(해당 글이 아닌)와 commit log의 링크 그리고 commit message를 트윗해준다.

![take 6](https://c2.staticflickr.com/6/5626/30496949926_e773e45c63_o.png)