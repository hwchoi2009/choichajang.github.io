---
title: "깃허브 블로그 만들기 삽질 #1"
date: 2019-01-22 21:57:00 -0400
categories: github jekyll blog
---

요즘 개발자 사이에 핫하다는 깃허브로 블로그 삼기에 동참하기로 했습니다.
그케 순서는 다음과 같이 두 단계입니다.

1. 깃허브 계정 생성
2. 깃허브를 블로그로 만들기

### 1. 깃허브 계정 생성
다음과 같이 두 단계입니다. 
--- 지메일 계정을 하나 파기(있으면 있는 계정 사용한다)
--- 깃허브(https://github.com/)에 접속해 계정을 생성하기

지메일 계정 생성 방법은 생략하겠습니다.
깃허브 계정 생성 방법 진유림 님의 웹북([초심자를 위한 Github](http://www.realhanbit.co.kr/books/125/pages/1129/preview))을 참고하기 바란다.
(계정 생성하시고 꼭 본인 지메일에서 '[GitHub] Please verify your email address.' 글을 확인하시고 'Verify email address' 단추를 누르세요)

### 2. 깃허브를 블로그로 만들기
다음과 같이 단계입니다.

1. 리포지터리 생성하기
2. 테마 적용하기

리포지터리는 아래 형식으로 만듭니다.

**본인계정이름.github.io**

저는 계정이 ChoiChaJang입니다. 그래서 다음과 같은 리포지터리를 만들었습니다.

**coichajang.github.io**

위와 같은 형식을 따라야지만 coichajang.github.io와 같이 간단한 URL을 블로그 주소를 쓸 수 있습니다.
형식을 따르지 않으면 다음과 같은 URL 형식으로 접속해야 합니다.

**coichajang.github.io/리포지터리이름**

근데 프로젝트를 만들어서 뭔가 설정을 해야 한다고 하네요(자세한 방법은 [쉽고 빠르게 수준 급의 GitHub 블로그 만들기 - jekyll remote theme으로](https://dreamgonfly.github.io/2018/01/27/jekyll-remote-theme.html) 참조).
그러니 꼭! 형식을 따라주세요.



### 3. 테마 적용하기
_config.yml 파일 생성하기
--- _posts에 첫 번째 글 올리기
--- 
(반드시 본인 깃허브 계정과 같은 이름 + .github.io 형식으로 합니다.)

```python
def print_hi(name):
  print("hello", name)
print_hi('Tom')
'''
