---
title:  "Spring Chapter 1. Spring 소개와 학습 안내"

categories:
  -  Spring Lession 1

toc: true
toc_sticky: true

date: 2020-12-09
last_modified_at: 2020-12-09
---
출처 : 뉴렉처 강의 <http://www.newlecture.com>

***
## Spring Framework의 핵심 기능
- Dependency injection (DI)
- Transaction management
=> 기존의 java EE의 영역을 Spring으로 대체함 (가격의 유료화...)

***
## 웹을 위한 Spring Framework 모듈
- <b>MVC</b> - DI
- <b>트랜잭션</b> - AOP
- <b>인증과 권한</b> - Servlet Filter

***
## DI (Dependency injection)
- 부품 조립을 의미함
```
// 일체형(Composition) has a
class A {
  private B b;

  public A() {
    b = new B();
  }
}

// 조립형(Association) has a
class A {
  private B b;

  public void setB(B b) {
    this.b = b;
  }
}
```
기업에서는 조립형 방식을 사용!!

***
## IoC(Inversion of Control) Container
- 객체를 관리하고, 객체의 생성을 책임지고, 의존성을 관리하는 컨테이너
- 부품이 생성될 때 small -> large 순으로 부품 생성
- 일체형에서는 의존성에 따라 순차적으로 부품 생성 (A -> B -> C)
- 조립형에서는 역순으로 부품 생성 (C -> B -> A)

***
