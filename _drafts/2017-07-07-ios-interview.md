---
layout: post
title:  "iOS Interview"
date:   2017-07-07 23:30:00 +900
categories: [Swift]
tags: [ios, swift, interview]
---

1. strong, weak, copy의 차이

	* strong는 참조 카운트가 증가될 것이고 그것에 참조는 그 객체의 생명주기를 통해 유지될 수 있음을 의미한다.
	* weak는 객체에 포인터를 가리키고 있지만 잠조 카운팅을 올리진 않는다. 부모 자식 관계가 만들어질때 종종 사용된다. 부모는 자식에게 strong 참조를 가지지만 자식은 부모에게 weak 참조를 가지게 만든다.
	* copy는 객체가 생성될때 객체의 값을 복사한다는 의미이다. 또한 변경으로부터 값을 보호한다.

2.  frame과 bounds의 차이는 무엇인가?

	* UIView의 bounds는 그 고유 좌표 시스템 (0, 0)에 연관된 position (x, y)와 size (width, height)로 표현되는 사각형이고,
	* UIView의 frame은 그 뷰를 담고있는 부모뷰에 연관된 position (x, y)와 size (width, height)로 표현되는 사각형이다.

3. Responder Chain이란 무엇인가?

	* ResponderChain은 받은 이벤트에 응답하기위한 기회를 가진 객체들의 계층

4. 디자인 패턴이 왜 중요한가?

	* 디자인 패턴은 소프트웨어 설계에서 흔히 만나는 문제들에대한 재사용가능한 솔루션이다. 이것은 이해하기 쉽고 재사용하기 쉬운 코드를 짜는데 도움을 주기위한 설계의 템플릿이다. 아래는 아주 일반적인 Cocoa 디자인 패턴들이다.
		* 생성 : 싱글톤
		* 구조 : MVC, Decorator, Adapter, Facade
		* 동작 : 옵져버, Memento

5. 스위프트스위프트의 주 이점은 무엇인가?

	* 옵셔널타입, 앱의 크레쉬를 방지해준다
	* 내장된 에러 핸들링
	* 클로저
	* 다른 언어에비해 빠르다
	* 타입-세이프 언어
	* 패턴 매칭을 지원한다

6. [weak self]와 [unownded self]를 설명하라
unowned는 한가지만 빼고서 weak와 같다. 바로, 이 변수는 nil이 될 수 없다는 것이고 그러므로 이 변수는 절때 옵셔널이 될 수 없다.

그러나 그 인스턴스가 메모리 해제된 후에 변수에 접근하려하려한다면, 인스턴스가 메모리 해제된 후에 절때 그 변수를 사용하지 않을것이라고 확신할때만 unowned를 사용해야한다.

그러나 변수를 weak로 만들고 싶지 않고 해당 인스턴스가 메모르 해제된 후에 그 변수에 접근하지 않을 확신이 있을때 unowned를 사용할 수 있다.

[weak self]로 정의하면, 클로저 내의 어떤 부분이 nil일 수도 있는 경우를 다룰 수 있게 해주므로 변수는 반드시 옵셔널이여야한다. 비동기 네트워크 요청에서 [weak self]를 쓰는 경우는 그 요청이 빈번하게 사용되는 뷰의 View Controller에서 이다.

7. 뷰컨트롤러의 라이프사이클 이벤트 순서를 설명하라
몇몇 다른 라이프사이클 이벤트가 있다.

- loadView
컨트롤러가 관리하는 뷰를 만든다. 이것은 뷰컨트롤러가 생성되고 순차적으로 완성되었을때만 호출된다.

- viewDidLoad
컨트롤러의 뷰가 메모리에 올라간 뒤에 호출된다. 뷰가 생성될때만 호출된다.

- viewWillApear
화면에 뷰가 표시될때마다 호출된다. 이 단계는 뷰는 정의된 바운드를 가지고 있지만 화면회전은 적용되지 않는다.

- viewWillLayoutSubviews
뷰컨트롤러에게 그 자식뷰의 레이아웃을 조정하는 것에 대한 것을 알려주기위해 호출된다. 이 메소드는 frame이 바뀔때마다 호출될 것이다.

- viewDidLayoutSubviews
뷰가 그 자식 뷰의 레이아웃에 영향을 준 것을 뷰컨트롤러에 알려주기 위해 호출된다. 뷰가 그 자식뷰의 레이아웃을 바꾸고난 뒤에 추가적인 변경을 하고싶으면 여기서 하면된다.

- viewDidAppear
뷰가 뷰 계층에 추가되었다고 뷰컨트롤러에 알려준다.

- viewWillDisappear
다음 뷰컨트롤러로 트랜지션하기 전에 일어나며, 기존의 뷰컨트롤러가 화면으로부터 사라지기 전에 이 메소드가 호출된다.

- viewDidDisappear
뷰컨트롤러가 화면에서 사라지고나면 이 함수가 호출된다. 뷰컨트롤러가 화면에 없을때, 실헹시키지 않을 작업들을 중지시키는 용도로 이 메소드를 오버라이드한다.

8. iOS 앱 상태는 무엇이 있나?
Non-running : 앱이 실행되지 않고 있음
Inactive : 앱이 포그라운드에서 실행되고 있으나 이벤트는 받지 않음. iOS앱은 inactive 상태로 들어갈 수 있는데, 전화나 SMS 메시지를 받을때가 그 예이다.
Active : 앱이 포그라운드에서 실행되며 이벤트도 받고 있음.
Background : 앱이 백그라운드에서 실행되고 코드를 실행하고 있음.
Suspended : 앱이 백그라운드에 있으나 코드가 실행되지 않음.

9. atomic과 nonatomic synthesized 프로퍼티의 차이에대해 설명하라
atomic : 디폴트 동작이다. 한 오브젝트가 atomic으로 선언되있으면 스레드 세이프하게된다. 스레드 세이프의 의미는, 클래스의 특정 인스턴스의 한 스레드만 그 오브젝트에대해 조작할 수 있다.
nonatomic : 스레드 세이프 하지 않다. nonatomic 프로퍼티 속성을 사용하면 synthesized 접근자가 간단하게 직접 값을 세팅하거나 리턴하도록 지정할 수 있다. 서로 다른 스레드에서 동시에 같은 값에 접근하려 할때 어떤 일이 일어날지는 보장하지 못한다. 이런 이유로, atomic보다 nonatomic이 접근 속도가 더 빠르다.

10. 