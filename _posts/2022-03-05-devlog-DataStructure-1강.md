---
layout: post
title:  "[자료구조] "
subtitle:   "lecture 1"
categories: devlog
tags: DataStructure
---

- 자료구조?

- 자료구조의 적용과 응용

___

- 이론/요소
    - 현실 세계의 실제 자료들의 관계를 반영할 수 있는 방법을 배운다.
    - 자료를 효율적으로 처리할 수 있게 표현하는 방법을 배운다.


- 실습
    - 자료 구조로 표현된 자료를 처리하는 절차들의 모임인 알고리즘의 작성 예시에 대해 배운다.
    - 다양한 문제들을 자료 구조로 해결해본다.    


  
- Fundamentals of Data Structures in C++ (Horowitz, Sahni, Mehta)
- 보조 교재
    - 자바로 자료구조를 설명한 모든 서적
    - 국내 자료구조 관련 도서

---

### 자료구조 개요

- 자료구조란?
    - 컴퓨터 프로그램을
    - 논리적인 구조로 설계하고 분석
    - 컴퓨터가 필요로 하는 자료

    -> 표현, 저장, 처리하는 일련의 구조와 방법

![자료구조 개요1 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%941.png)

- 컴퓨터로 문제를 해결하는 과정

![자료구조 개요2 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%942.png)

- 문제 정의 = 요구사항 + 분석

- 요구사항?
    - 입력 : 우리에게 주어진 정보 / 출력 : 우리가 만들어야 하는 결과

- 분석?
    - 문제를 잘게 쪼개기! (해결 가능한 / 관리 가능한 수준까지)
    - 방법 : 상향식(BOttom-Up) / 하향식(Top-Down)

- 분석: 상향식
    - 구조화된 전략 없음
    - 쪼개진 문제 단위로 먼저 해결하기

- 분석: 하향식
    - 목적에 맞게 프로그램이 어떻게 동작해서 종료할 지 계획
    (프로그램을 여러 단위 부분 조각으로 나눠가며 해결)

- 분석 후에는? **설계(DESIGN)**

    - 처리 대상 결정
        - **데이터 객체** : 프로그램에 필요한 요소
        - 어떻게 추상화하고 표현할까? -> **자료정의**
    
    - 처리 방식 결정
        - **처리** : 데이터 객체를 다루기
        - 알고리즘 설계 -> 알고리즘 명세에 따라 처리 -> **알고리즘 작성**

- **반복 정제(REFINEMENT)** 후 코딩
    - 선택한 데이터 객체를 표현하기
    - 알고리즘에 따라 작성하기

- **순서가 중요함!**
    - 데이터 객체의 표현이 결정되야 -> <u> 알고리즘을 효과적</u>으로 작성할 수 있다.

- 마지막은 검증(VERIFICATION)
    - 정확성 입증
    &nbsp;&nbsp;&nbsp;&nbsp; - 선택한 알고리즘이 정확한가?
    &nbsp;&nbsp;&nbsp;&nbsp; - 에러율을 줄이고 있느가?

    - 테스팅
    &nbsp;&nbsp;&nbsp;&nbsp; - 에러가 없는 프로그램이 목표
    &nbsp;&nbsp;&nbsp;&nbsp; - 테스트 데이터 집합을 이용해 검증

- 에러 제거
     - 설계와 코딩에 따라 오류 제거의 난이도가 결정됨
     - **잘 설계되고 모듈화된 프로그래밍을 하자!**

- 결론 : 문제를 잘 해결하려면?

    - **요구사항**을 찾고
    - **분석**GKDU
    - 적절한 **데이터 객체(자료구조)**를 선택하고 알고리즘을 **설계**하고
    - 문제에 적합하게 **정제**하여 **코딩**한 후
    - 그리고 <u>에러 없이</u> 문제를 잘 해결하는지 <u>테스트</u>하여 **검증**하기 

- 소프트웨어 생명주기 

![자료구조 개요3 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B7%9C%EC%A1%B0%20%EA%B0%9C%EC%9A%943.png)

생명주기를 잘 관리하는 방법

- 소프트웨어 공학 방법론
    - 폭포수 모델 (전통적인 방법)
    - 점진적 모델 : 기능을 점진적으로 증가시키는 방법, 각 기능별로 생명주기 관리
    - 오픈소스 개발 방법
    - 애자일 방법론 : 수시로 변경되는 요구사항에 맞춰 프로토타입을 만들고 검증하여 적용하는 방법

### 알고리즘

- 알고리즘?
    - **유한(finite)한** 명령어의 집합 -> 명령어에 따라 특정한 일(Task)를 수행

- 알고리즘이 가져야할 것

     - 입력(Input) - 외부에서 제공하는 0개 이상의 입력이 존재해야 한다!
     - 출력(Output) - 최소한 하나 이상의 출력 결과를 생성해야 한다.
     - 확실성(Definiteness) - 수행할 단계와 순서를 완전하고 명확하게 명세해야한다. 각 명령어가 명확하고 애매모호하지 않아야 한다.
     - 유한성(Finiteness) - 유한한 단계를 거친후 반드시 종료해야 한다.
     - 효과성(Effectiveness) - 모든 명령어는 효율적으로 실행 가능해야 한다.

- 알고리즘 vs 프로그램

![자료구조 개요4 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%944.png)

- 알고리즘을 표현할 수 있는 방법 -> 자연어, 순서도, 의사코드 (C-Style 등)

 - 알고리즘 표현의 예시 - 선택 정렬

 목표 : 1 이상의 정수 집합을 정렬하기 (정렬되지 않은 숫자들에서 가장 작은 숫자를 찾아서 정렬된 결과에 두기)

 위의 목표는 확실성에 부합하지 않기에 잘못된 알고리즘 표현 방식임
    - 정렬되어 있는 숫자들이 주어지면 어떻게 하나요?
    - 정렬된 결과에 어떻게 둬야하나요?

 의사코드로 표현해보면

![자료구조 개요5 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%945.png)

 - 알고리즘 표현의 예시 - 이진 탐색
  
  1. 1 시앙의 정수 집합이 있고  
  2. 이 집합이 이미 정렬되어 있는 자료를 list라고 한다.  
  3. 정수 searchnum이 이 집합에 있는 지 확인한다.  
  4. 만약 찾으면 list 에서의 index값을 얻는다.  
  (예를 들어, list[i]가 searchnum가 같으면, i가 된다.)  
  5. 그렇지 않으면, -1이 된다.

![자료구조 개요6 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%946.png)
 - 알고리즘 표현의 예시 - 재귀 알고리즘

 작성한 알고리즘(함수 등)이 자기 자신을 호출하는 알고리즘 (직접 재귀, 간접 재귀)

 - 복잡한 절차를 단순하게 표현할 수 있다
    - 어떤 함수도 재귀적으로 표현 가능
    - 재귀적으로 정의된 문제에서는 좋음!

![자료구조 개요7 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%947.png)

- 반복적(ITERATIVE) 표현을 재귀적(RECURSIVE)으로 변경하기
    - 재귀적 호출을 종료하는 **경계 조건**을 만들기!
    - 반복적 표현의 각 단계를 재귀적 호출로 바꾸기

![자료구조 개요8 사진](https://github.com/ehyeok9/ehyeok9.github.io/blob/master/assets/img/devlog/data-structure/lecture1/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0%20%EA%B0%9C%EC%9A%948.png)

### 데이터 추상화

- 현실 세계를 자료형으로 표현하여 추상화 하는 것.
    - 기본 자료형 (정수, 실수, 문자 등)
    - 배열 (동일한 원소들의 집합)
    - 복잡한 구조 (여러가지 자료형들을 복합적으로 포함하는 원소)

- 자료형(DATA TYPE)
    - 객체(의 모음)
    - 이 객체에 대한 <u>연산자</u>

- Abstract Data Type(ADT)
    - 객체의 명세에 따라 만든 자료형
    - 이 자료형에 <u>대한 연산자</u> (구현과는 분리됨)


- Abstract Data Type(ADT) - 예시 
    - ex) SET(집합) -> 연산자 (합집합, 교집합 등)

- Abstract Data Type(ADT)
    - ADT는 프로그램의 일부분에 한정되도록 자료형으로 캡슐화
    - ADT의 구현은 프로그래밍 언어에 맞게 작성
    (구현은 ADT를 잘 나타내는 자료구조를 선택한다.)
    (자료구조는 기본 프로그래밍 언어에서 표현되는 기본 자료형으로 구성한다.)

- Abstract Data Type(ADT) - 자연수 예시

- 겍체 : 0 ~ MAX_INT 정수의 정렬된 범위
- 연산자 : 자연수 - Zero() / Boolean - Is_Zero() / 자연수 Add(x, y) 등 

