---
title: 백로그 계층 구조 정리 (Epic, Story, Task, Subtask)
date: 2026-04-01
categories: [Development, Methodology]
tags: [agile, scrum, epic, user-story, task, jira, 개발방법론]
---

## 왜 계층을 나누는가?

기능을 한 덩어리로 관리하면 진행 상황을 파악하기 어렵다.

- "회원 기능 개발" 이라는 작업 하나는 언제 끝날지 가늠이 안 된다
- 너무 잘게 나누면 큰 그림이 안 보인다
- 큰 단위에서 작은 단위로 계층을 나눠야 전체 진행률도 보이고, 당장 오늘 뭘 해야하는지도 보인다

```
Epic
└── Story
     └── Task
          └── Subtask
```

## 1. Epic

> 하나의 큰 기능이나 목표를 나타내는 최상위 단위

- 여러 Sprint에 걸쳐 완료되는 큰 작업 묶음이다
- "무엇을 만드는가"를 큰 그림으로 표현한다
- 하나의 Epic 아래에 여러 Story가 달린다

**예시**
- 회원 기능
- 결제 시스템
- 알림 기능
- 관리자 대시보드

> Epic은 그 자체로 개발하는 단위가 아니다. Story로 쪼개져야 실제 작업이 된다.

---

## 2. Story

> 사용자가 원하는 것을 사용자 관점에서 표현한 기능 단위

- 하나의 Epic을 사용자 입장에서 잘게 나눈 것이다
- 보통 **하나의 Sprint 안에 완료**할 수 있는 크기로 작성한다
- 각 Story 마다 구현을 위한 개발규모 추정치인 Story Point를 명시한다

**작성 형식**
```
As a [사용자 유형],
I want to [원하는 기능],
so that [이유/목적].
```

**예시 (Epic: 회원 기능)**
- 사용자는 이메일로 회원가입을 할 수 있다
- 사용자는 이메일과 비밀번호로 로그인할 수 있다
- 사용자는 비밀번호를 재설정할 수 있다
- 사용자는 회원 탈퇴를 할 수 있다

**좋은 Story의 기준 - INVEST**
- **I**ndependent — 다른 Story에 의존하지 않는다
- **N**egotiable — 세부 구현은 협의 가능하다
- **V**aluable — 사용자에게 가치가 있다
- **E**stimable — 작업량을 추정할 수 있다
- **S**mall — 하나의 Sprint 안에 끝낼 수 있다
- **T**estable — 완료 여부를 확인할 수 있다

### 2.1. Story Pint

> Story의 복잡도, 난이도, 작업량을 상대적인 수치로 표현한 것

- 시간(몇 시간, 며칠)으로 추정하지 않고 포인트로 표현한다
- 피포나치 수열을 주로 사용한다
```
1, 2, 3, 5, 8, 13, 21 ...
```
- 작업이 클수록 불확실성도 커지기 떄문에 간격을 크게 둔다
- 예: 1포인트(매우 간단) / 3포인트(보통) / 8포인트(복잡) / 13포인트(매우 복잡, 쪼개는 걸 고려)

## 3. Task

> Story를 구현하기 위해 개발자가 해야 하는 구체적인 작업

- Story가 "무엇을 만들어야 하는가"라면, Task는 "어떻게 만들 것인가"다
- 하나의 Story는 여러 Task로 나뉜다
- 보통 하루 이내에 끝낼 수 있는 크기로 쪼갠다
- 담당자를 Task 단위로 지정한다

**예시 (Story: 사용자는 이메일로 회원가입을 할 수 있다)**
- 회원가입 API 엔드포인트 구현
- 이메일 중복 검사 로직 구현
- 비밀번호 암호화 처리
- 회원가입 API 테스트 코드 작성

---

## 4. Subtask

> Task가 너무 클 때, 더 작은 단위로 나눈 것

- Task 안에서 체크리스트처럼 사용하는 경우가 많다
- 모든 Task에 Subtask가 필요한 건 아니다 (Task가 이미 충분히 작으면 생략해도 된다)

**예시 (Task: 회원가입 API 엔드포인트 구현)**
- Request DTO 작성
- 예외 처리 추가

---

### 참고 자료
[epic, story, subtask 작성법](https://seanthepm.tistory.com/entry/Jira%EC%97%90%EC%84%9C-%EC%B5%9C%EC%84%A0%EC%9D%98-%EA%B2%B0%EA%B3%BC%EB%A5%BC-%EB%A7%8C%EB%93%A4%EC%96%B4%EB%82%B4%EB%8A%94-%EB%8D%B0-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%97%90%ED%94%BD-%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%84%9C%EB%B8%8C%ED%83%9C%EC%8A%A4%ED%81%AC-%EC%9E%91%EC%84%B1%EB%B2%95)

[Jira로 스크럼 스프린트 운영](https://seanthepm.tistory.com/entry/Jira%EB%A1%9C-%EC%8A%A4%ED%81%AC%EB%9F%BC-%EC%8A%A4%ED%94%84%EB%A6%B0%ED%8A%B8-%EC%9A%B4%EC%98%81%ED%95%98%EA%B8%B0)
