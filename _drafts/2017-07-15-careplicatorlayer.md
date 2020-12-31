---
layout: post
title:  "CAReplicatorLayer"
date:   2017-07-15 23:30:00 +900
categories: [Swift]
tags: [ios, swift, animation, layer, coreanimation]
---

텀블러의 loading indicator를 구현하기 위해 `CAReplicatorLayer`를 알아봤다.

## CAReplicatorLayer

> A layer that creates a specified number of copies of its sublayers (the source layer), each copy potentially having geometric, temporal, and color transformations applied to it.

애플의 공식 문서의 설명을 보면 sublayer의 기하학적, 시간적 및 색상 변형등 이 적용된 복사본을 만들어 주는 layer라고 한다.

## Property

텀블러의 loading indicator를 구현하기 위해 사용한 `CAReplicatorLayer`의 Property를 알아보자.

* var instanceCount: Int

    원본이 되는 `CALayer`을 얼마만큼 복사할 것인지를 결정
    
* var instanceDelay: CFTimeInterval

    다음 복사될 `CALayer`간의 에니메이션을 시작할 간격을 초 단위로 지정
    
* var instanceTransform: CATransform3D

    다음 복사될 `CALayer`를 이전의 `CALayer`와 어떻게 변환할 것인지를 지정(위치나 각도 등을 조절할 때 사용)




