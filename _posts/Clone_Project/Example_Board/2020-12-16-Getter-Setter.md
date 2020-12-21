---
title: "생성자(Constructor), Getter/Setter"

categories:
  - Example_Board

toc: true
toc_sticky: true

date: 2020-12-16
last_modified_at: 2020-12-16
---

출처 : https://maktooob.tistory.com/35

## 생성자

- 객체가 생성될 때 자동으로 실행되는 특수한 메소드
- return형 명시 x
- 클래스와 이름 동일
- 오버로딩 가능

```
class Article {
  int seq; // 글 번호
  String subject; // 글 제목
  String writer; // 작성자

  public Article(int seq, String subject, String writer) {
    this.seq = seq;
    this.subject = subject;
    this.writer = writer;
  }

  public void print() {
    System.out.println(this.seq);
    System.out.println(this.subject);
    System.out.println(this.writer);
  }
}

public class Exam {
  public static void main(String[] args) {
    Book b = new Book();
    b.read();
    Article article1 = new Article(1, "자바연습1", "김갑돌");
    article1.print();
    System.out.println("--------");

    Article article2 = new Article(2, "자바연습2", "김갑순");
    article2.print();
  }
}
```

## Getter / Setter

- 객체들이 데이터(필드)를 외부에서 직접적으로 접근하는 것을 막음 (객체 무결성 보장)
- 데이터(필드)들은 private 접근 제한자로 막아두고, 각 필드의 Getter, Setter로 접근하는 방식을 취함

```
class Student {
  // 은닉된 맴버변수 => 현재 블록안에서만 접근 가능
  private String name;
  private int age;

  // 은닉된 맴버 변수에 값을 넣는 방법 => 메소드 사용
  public void setName(String name) {
    this.name = name;
  }
  public void setAge(int age) {
    this.age = age;
  }

  // 은닉된 맴버 변수의 값을 읽는 방법
  public String getName() {
    return name;
  }
  public int getAge() {
    return age;
  }
}

public class Exam3_getter_setter {
  public static void main(String[] args) {
    Student s = new Student();
    s.setName("김갑돌");
    s.setAge(20);

    String name = s.getName();
    System.out.println("이름 : " + name);

    int age = s.getAge();
    System.out.println("나이 : " + age);
  }
}
```

***
