---
layout: post
title:  "Nil Coalescing Operator"
date:   2015-12-28 12:16:00 +0900
categories: swift
---

Raywenderlich의 Tutorial을 따라 하던 중에 잘 모르겠는 연산자가 보여서 정리
바로물음표 두개로 표현한 연산
`rings[.Inner]?.value ?? 0`

이 녀석의 이름은 Nil Coalescing Operator

표현식은 `(a ?? b)`

해석하자면 a가 nil일 경우 default value인 b을 반환하고, nil이 아닐 경우 a 를 반환
a의 경우 항상 optional type
b는 a의 type에 저장될 수 있는 type

이 연산자는 `a != nil ? a! : b` 형태의 축약