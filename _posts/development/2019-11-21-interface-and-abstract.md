---
date: 2019-11-21 19:11:00
layout: post
title: 인터페이스와 추상 클래스 차이
subtitle: 인터페이스와 추상 클래스 차이
description: >-
	인터페이스와 추상 클래스의 차이를 알아보자.
category: development
tags:
  - development
  - interface
  - abstract class
  - virtual function
author: Stop_Male
paginate: true
---

## 가상함수

### 일반 가상함수


- 인터페이스 + 함수의 선언(내부 구현)

- 이 기능을 물려줄테니, 니가 선언 안해도 내가 기본적으로 기능이 돌아가게 해줄께.

```c++
virtual void function()
{
...
}
```

### 순수 가상함수

* 인터페이스(함수의 내부가 구현되어 있지 않음)
* 이 기능은 꼭 있어야 하니까, 니가 반드시 내부를 구현해서 사용해야해.

```c++
virtual void function() = 0;
```



## 추상 클래스

### 목적

* 기존의 클래스에서 공통된 부분을 추상화하여 상속하는 클래스에게 구현을 강제화.
* 메소드의 동장을 구현하는 자식 클래스로 책임을 위임.
* 공유의 목적.

### 특징

* 하나 이상의 순수 가상함수로 이루어져 있다.
* 객체 지향 프로그래밍에서 중요한 특징인 다형성을 가진 함수의 집합을 정의할 수 있게 해준다.
* 인스턴스를 생성할 수 없다.
* 하지만, 추상 클래스 타입의 포인터와 참조는 바로 사용할 수 있다.

### 용도 제한

* 변수 또는 멤버 변수
* 함수의 전달되는 인수 타입
* 함수의 반환 타입
* 명시적 타입 변환의 타입

```c++
class cAbsClass
{
    virtual void function() = 0;
}
```

## JAVA에서의 추상 클래스와 인터페이스

### 공통점

* 선언만 있고 내부 구현이 없는 클래스이다.
* 따라서, 새로운 인스턴스를 생성할 수 없다.

### 차이점

* 추상클래스와 인터페이스의 차이점에서 키워드는 목적이다.
* 추상클래스의 목적
  * 클래스들의 공통적인 기능을 하는 객체들의 추상화.
  * 포유류, 양서류, 조류와 같은 동물들의 공통적인 기능을 가진 동물 클래스.
  * 동물의 행동 : 먹다. 걷다. 뛰다 같은 공통적인 사항을 추상화하여 가지고 있다.
* 인터페이스의 목적
  * 특정 클래스에서 필요로 하는 기능을 추상화.
  * 포유류는 젖을 먹이지만, 조류와 양서류는 그렇지 않다.
  * 만약 젖을 먹이는 행위가 추상클래스인 동물 클래스에 선언되어 있다면, 양서류와 조류 또한 반드시 해당 함수를 구현해야 한다.
  * 즉, 추상클래스와 인터페이스의 목적의 차이가 여기서 발생된다. 모든 포유류는 반드시 젖을 먹이는 기능을 가지고 있어야 하기 때문에, 동물 클래스를 상속받고 추가로 필요로한 젖을먹인다 인터페이스를 상속받아 구현하게 된다.