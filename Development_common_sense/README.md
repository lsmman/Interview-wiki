# 개발상식

* [TDD](#TDD)

[뒤로](https://github.com/lsmman/Interview-wiki)

---

## TDD

테스트가 주도하여 개발을 이끌어나가는 형태의 개발론

테스트를 개발 이후에 수행하는 기존 방법과는 다르게, 테스트케이스를 먼저 작성한 이후 실제 코드를 개발하는 리팩토링 절차를 밟게 된다.

![요구사항 분석 - 테스트 코드 작성 - 코드 구현 - 리팩토링의 과정으로 진행된다.](https://camo.githubusercontent.com/6597fa05836444beab3afcbc7e8fbe59244bff8f/68747470733a2f2f6d626c6f677468756d622d7068696e662e707374617469632e6e65742f4d6a41784e7a41324d6a68664d6a45332f4d4441784e446b344e6a41324e5445784e4467772e667038584639795f5f4b7a37356e3836786b6e495044746854486a3961385130386f63494a49714d523641672e32346a4a615f385f5430516a3034503632465a6263687174386f544e584746534c5549747a4d5039357338672e504e472e73757265736f6674746563682f696d6167652e706e673f747970653d77383030)

### TDD의 장점

`Divided and Conquer`

개발에 필요한 요구사항 분석과 프로그래밍 스킬이 필요한 코드 개선을 분리하여 수행 가능하다. 

요구사항에 따른 프로그램 디자인과 그에 따른 테스트 코드 작성, 기능 구현, 리팩토링을 과정을 나누어 진행하기 때문에, 각각의 과정을 더 명확하게 처리할 수 있다.결과적으로 안전한 프로그래밍이 가능해진다.

- 짧은 개발 주기를 통해 고객의 요구사항 빠르게 수용 가능. 피드백이 가능하고 진행 상황 파악이 쉬움

- 자동화 도구를 이용한 TDD 테스트케이스를 단위 테스트로 사용이 가능함

### 비용/일정상 TDD를 모든 코드에 도입할 수 없다면?

`핵심코드 위주로 테스트 코드 도입`

테스트 코드를 작성하는 부분에서 생산성이 저하될 가능성이 있다. 그렇기 때문에 실무에서는 모든 기능에 대해 테스트 코드를 작성하는 것은 어려울 수 있다.

핵심기능에 대해 우선적으로 테스트를 작성하면 된다. 핵심기능이라는 것은 서비스 이용에 필수적으로 필요한 기능을 의미한다.

예를들어, 회원가입에서 아이디 중복체크는 회원가입을 할 때, 반드시 필요한 기능이다. 그렇지만, 섬네일 등록하는 것은 필요한 기능이지만, 이 기능이 없다해서 회원가입이 되지는 않는다. 이런 기능에 대해서는 테스트 코드의 우선순위를 낮추는 방식으로 현실적인 비용/일정에 맞춘다.

## Visit

```
2021.09.17 TDD
```
