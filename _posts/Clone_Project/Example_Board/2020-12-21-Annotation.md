---
title: "Annotation"

categories:
  - Example_Board

toc: true
toc_sticky: true

date: 2020-12-21
last_modified_at: 2020-12-23
---

출처 : https://palyoung.tistory.com/72

## Annotation

- @를 이용
- java코드에 주석을 달아 특별한 의미를 부여한 것
- 컴파일러가 특정 오류를 억제하도록 지시하는 것과 같이 프로그램 코드의 일부가 아닌 프로그램에 관한 데이터를 제공, 코드에 정보를 추가하는 정형화된 방법
- 사용 이유
  - 해당 데이터들에 대한 유효 조건을 쉽게 파악 가능
  - 코드의 양 줄어듬
- 종류
  - <strong>Built-in Annotation</strong> : JDK 내장
  - <strong>Meta Annotation</strong> : Annotation에 대한 정보를 나타냄
  - <strong>Custom Annotation</strong> : 개발자가 직접 만들어 내는 것

## Board 내 주요 Annotation
@Controller
프리젠테이션 레이어, 웹 어플리케이션에서 웹 요청과 응답을 처리하는 클래스

@GetMapping
요청 URL을 어떤 메서드가 처리할지 mapping해주는 annotation (== @RequestMapping(value = "", method = RequestMethod.GET))

@Getter @Setter

```
@Getter
@Setter
private String name;
```

위와 같이 특정 필드에 Annotation을 붙여주면, 다음과 같이 자동으로 생성된 접근자와 설정자 메소드를 사용할 수 있다.

```
user.setName("홍길동");
String userName = user.getName();
```

@NoArgsConstructor
파라미터가 없는 기본 생성자 생성  
JPA에서는 proxy를 생성하기 위해 기본 생성자 1개를 반드시 생성해야함.

```
// 잘못된 사용법
@NoArgsConstructor(access = AccessLevel.PUBLIC)
```

위와 같이 기본 생성자를 Public으로 열어두게 되면 객체 생성 시 안전성을 심각하게 떨어뜨릴 수 있음

```
// 올바른 사용법
@NoArgsConstructor(access = AccessLevel.PROTECTED)
```

@Entity
JPA를 사용해서 테이블과 Mapping할 클래스를 명시

```
// JPA에서 사용할 Entity 이름을 지정 (기본값 : 클래스 이름을 그대로 사용)
@Entity(name = "Member")
```

@Id
해당 property가 테이블의 Primary Key 역할을 함

@GeneratedValue
Primary Key의 값을 위한 자동 생성 전략을 명시

@EnableJpaAuditing
JPA Auditing 기능을 사용하기 위해 명시
※ JPA Auditing : Spring Data JPA에서 시간에 대해서 자동으로 값을 넣어주는 기능

@ToString
toString() 메소드를 생성

```
// 원하지 않는 속성 제외
@ToString(exclude = "password")
```

@Transactional
- class, method 위에 추가되면, 이 class에 트랜잭션 기능이 적용된 proxy 객체가 생성
- 이 proxy 객체는 @Transactional이 포함된 method가 호출될 경우, PlatformTransactionManager를 사용하여 트랜잭션을 시작하고, 정상 여부에 따라 Commit, Rollback 함.
