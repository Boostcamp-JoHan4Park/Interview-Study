## What is the difference between list and tuples in Python?

Keyword: 수정 가능 여부  
Answer: List는 수정 가능하고 tuple은 수정이 불가능해 data corruption을 방지하며 iteration이 더 빠르고 memory를 적게 사용합니다.

- List: 수정 가능(mutable)
- Tuple: 수정 불가(immutable) data corruption 방지  
  iteration이 더 빠름  
  less memory

<br/>

## What are the key features of Python?

Keyword: interpreter language  
Answer: 파이썬은 interpreter language라 실행 전에 컴파일할 필요가 없습니다.

- python은 interpreter language이다. 실행전에 컴파일할 필요가 없음. 또한 동적 타이핑이다. 실행시간에 자료형을 검사 자료형 명시할 필요 없음.
- code convention, 함수형 프로그래밍의 개념을 사용함(lambda 같은 익명함수)

<br/>

## What type of language is python? Programming or scripting?

Keyword:  
Answer:

- 스크립트 언어이나, 프로그래밍 언어의 레벨까지 올라왔다고 봐도 무방
- 프로그래밍 언어인데 그 용도가 주로 운영체제 위에서 움직이는 새로운 프로그램을 만드는 것보다는, 기존에 존재하는 어떤 다른 프로그램들을 제어하기 위해 쓰이며 그 기존의 프로그램들 위에서 구동이 지원되는 언어들을 스크립트 언어
- Generally, all the scripting languages are considered programming languages. The main difference between both is scripting languages doesn’t require any compilation and are directly interpreted.

<br/>

## Python an interpreted language. Explain.

Keyword:  
Answer:

- 인터프리터(interpreter, 해석기)란 소스코드를 바로 실행하는 컴퓨터 프로그램 또는 환경을 말한다. 소스코드를 목적코드로 옮기는 컴파일과 대비된다
- 인터프리터는 소스코드를 한줄 한줄 읽어들이면서 실행하는 프로그램, 번역과 실행이 동시에 이루어집니다. 즉, 별도의 실행파일이 존재하지 않습니다.
- 컴파일하지 않고 즉시 실행됨
- 프로그래밍 언어 차원에서 동적인 기능을 지원하기 유리

<br/>

## What is pep 8?

Keyword: 협업을 위한 가이드, 규칙
Answer: 파이썬 코드를 어떻게 구상할 지 알려주는 스타일 가이드
다른 사람과 원활하게 협업하려면 공통된 스타일 공유가 필요 합니다.
일관성 있는 스타일은 나중에 수정하기 쉽습니다.

## How is memory managed in Python?

Keyword:
Answer: Python Memory Manager가 모든 메모리 관련 사항을 관리해준다. 모든 것을 객체로 치부한다. 따라서 C와는 다르게 메모리에 직접 값이 할당되지 않고, heap에 해당 object가 생성된 후에 stack에서 이를 가르키는 형태로 값이 할당된다.

- What is namespace in Python?
- What is PYTHONPATH?

---

## What does len() do?

입력값의 길이(요소의 전체 개수)를 돌려주는 내장함수

## What does [::-1] do?

처음부터 끝까지 역순으로 접근
