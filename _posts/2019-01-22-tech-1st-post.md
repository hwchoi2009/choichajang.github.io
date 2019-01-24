---
layout: post
title: "깃허브 블로그 만들기 삽질 #1 : 깃허브 개설하고 지킬 테마를 적용해 블로그 만들기"
date: 2019-01-22 21:57:00 -0400
categories: tech
---

요즘 개발자 사이에 핫하다는 깃허브로 블로그 삼기에 동참하기로 했습니다.
크게 순서는 다음과 같이 두 단계입니다.

1. 깃허브 계정 생성
2. 깃허브를 블로그로 만들기

## 1. 깃허브 계정 생성
다음과 같이 두 단계입니다. 
--- 지메일 계정을 하나 파기(있으면 있는 계정 사용한다)
--- 깃허브(https://github.com/)에 접속해 계정을 생성하기

지메일 계정 생성 방법은 생략하겠습니다.
깃허브 계정 생성 방법 진유림 님의 웹북([초심자를 위한 Github](http://www.realhanbit.co.kr/books/125/pages/1129/preview))을 참고하기 바란다.
(계정 생성하시고 꼭 본인 지메일에서 '[GitHub] Please verify your email address.' 글을 확인하시고 'Verify email address' 단추를 누르세요)

## 2. 깃허브를 블로그로 만들기
다음과 같이 단계입니다.

1. 리포지터리 생성하기
2. 테마 적용하기(기존 설정)

### 2.1리포지터리 생성하기
리포지터리는 아래 형식으로 만듭니다.

**본인계정이름.github.io**

저는 계정이 ChoiChaJang입니다. 그래서 다음과 같은 리포지터리를 만들었습니다.

**coichajang.github.io**

위와 같은 형식을 따라야지만 coichajang.github.io와 같이 간단한 URL을 블로그 주소를 쓸 수 있습니다.
형식을 따르지 않으면 다음과 같은 URL 형식으로 접속해야 합니다.

**coichajang.github.io/리포지터리이름**

근데 프로젝트를 만들어서 뭔가 설정을 해야 한다고 하네요(자세한 방법은 [쉽고 빠르게 수준 급의 GitHub 블로그 만들기 - jekyll remote theme으로](https://dreamgonfly.github.io/2018/01/27/jekyll-remote-theme.html) 참조).
그러니 꼭! 형식을 따라주세요.


### 2.2 테마 적용하기(기본 설정)
테마를 적용하고 작업 후에 아무것도 없으므로 첫 번째 글을 올리고, 네이게이션을 만들어 about이 노출되게 하는 것까지 진행해볼게요.

진행 순서는 다음과 같습니다.

1. 테마 적용하기
2.  번째 글 올리기
3. 네비게이션 구성하기
4. about 만들기

###2.2.1 테마 적용하기
[jekyll-theme](https://github.com/topics/jekyll-theme)를 사용합니다(아직 저도 다른 테마는 사용해본 적이 없어요. 이제 입문 3시간째입니다. 블로그에서 다 이 테마만 사용합니다. 일단은 따라하기!).

1. https://github.com/topics/jekyll-theme 이동하기
2. mmistakes / minimal-mistakes 테마 선택
3. _config.yml을 클릭하기
4. 'Raw' 단추를 눌러 소스만 깔끔하게 보기
5. 소스 전체 복사하기
6. 내 리파지터리 루트에서 'Create new File' 눌러 _config.yml 파일 생성하기
7. _config.yml 파일 내용으로 이미 복사해둔 내용 붙여넣기 및 커스텀
8. index.html 파일 복붙하기
9. 네비케이션 만들고 자기 소개페이지 수정하기

'7. _config.yml 파일 내용으로 이미 복사해둔 내용 붙여넣기 및 커스텀' 방법은 다음과 같습니다(14행부터 27행 내용입니다).


```html
remote_theme             : "mmistakes/minimal-mistakes"
minimal_mistakes_skin    : "default" # "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum", "sunrise"

# Site Settings
locale                   : "en-US"
title                    : "최차장의 다이어리"
title_separator          : "-"
name                     : "최차장"
description              : "저는 최차장입니다...길게 써도 됩니다"
url                      : "https://choichajang.github.io" # the base hostname & protocol for your site e.g. "https://mmistakes.github.io"
baseurl                  : "" # the subpath of your site, e.g. "/blog"
repository               : # GitHub username/repo-name e.g. "mmistakes/minimal-mistakes"
teaser                   : # path of fallback teaser image, e.g. "/assets/images/500x300.png"
logo                     : "/choichajang.github.io/최차장.png"
```


'8. index.html 파일 복붙하기'는 index.html을 복붙해 넣으면 됩니다. 방법은 _config.yml 파일과 같습니다.
(모든 홈페이지가 그렇듯 index 파일은 필요합니다)

'9. 네비케이션 만들고 자기 소개페이지 수정하기'는 네이게이션 파일을 만들고 자기소개 파일을 만들면 그만입니다.

먼저 _data/navigation.yml 파일을 아래 내용으로 만듭니다.

```html
# main links
main:
  - title: "About" # 네비게이션 바에 표시 되는 이름
    url: "/about/" # 클릭시 이동할 URL
  - title: "Category"
    url: /categories/
  # - title: "Sample Collections"
  #   url: /collection-archive/
  # - title: "Sitemap"
  #   url: /sitemap
```

그후 리파지터리 루트에 about.md 파일을 생성합니다. 내용은 원하시는 대로 하시면 됩니다.
제 about 파일을 참고하시기 바랍니다.

[최차장의 about.md 파일 보기](https://github.com/ChoiChaJang/choichajang.github.io/blob/master/about.md)

읽어 주셔서 고맙습니다.
