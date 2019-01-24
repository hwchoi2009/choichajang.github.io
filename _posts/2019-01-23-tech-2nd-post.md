---
layout: post
title: "깃허브 블로그 만들기 삽질 #2 : 로컬/원격 리파지터리 연동하기"
date: 2019-01-23 21:57:00 -0400
categories: tech
---

이번에는 깃허브 원격 리파지터리를 로컬 PC에서 관리하는 방법을 알아보겠습니다.
순서는 다음과 같습니다.

1. 깃허브 관리 프로그래밍 다운로드
2. 원격 저장소 내려받기
3. 로컬에서 뭔가 변경하기
4. 원격 저장소에 변경 사항 저장하기

## 1. 깃허브 관리 프로그래밍 다운로드
원격 저장소를 관리하는 데 사용하는 https://git-scm.com를 내려받겠습니다.
저는 윈도우 기반이라 다음 UTL에 접속해 윈도우용 설치 파일을 내려받겠습니다. 접속만 하면 자동으로 설치 파일이 다운로드됩니다.

- https://git-scm.com/download/win

내려받은 파일을 더블클릭해 기본 설치를 진행합니다.

## 2. 원격 저장소 내려받기
Git Bash를 눌러 명령행을 실행합니다.
choichajang.github.io 리파지터리를 로컬에 저장합니다.

```bash
$ git clone https://github.com/ChoiChaJang/choichajang.github.io
Cloning into 'choichajang.github.io'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 155 (delta 0), reused 0 (delta 0), pack-reused 151
Receiving objects: 100% (155/155), 344.12 KiB | 214.00 KiB/s, done.
Resolving deltas: 100% (71/71), done.
```
이제 로컬에 리파지터리가 다운로드되었습니다.

## 3. 로컬에서 뭔가 변경하기
뭔가 변경하려면 어디에 리파지터리가 저장되었는지 알아야겠죠?
로컬 어디에 리파지터리가 저장되었는지 pwd 명령어로 확인합니다.

```bash
$ pwd
/c/Users/{사용자이름}
```

현 위치 아래 choichajang.github.io 파일이 있을 것 같습니다.

탐색기를 열어 이동해봅니다.
저는 이미지 파일들의 이름을 정리하고 _img 폴더를 만들어 해당 폴더로 이동시켰습니다.
여러분도 원하는 파일에 무언가 수정을 가해보세요.

## 4. 원격 저장소에 변경 사항 저장하기
git bash의 위치를 choichajang.github.io 리파지터리로 이동합니다.

```bash
$ cd choichajang.github.io/
```

이제부터 본격적으로 로컬에서 변경 사항을 원격 저장소에 반영하겠습니다.
총 3단계입니다(본인이 누군지 이미 밝혀져 있으면 입력할 필요가 없어요).

1. 수정 사항 모으기 - add
2. 본인 입력 - git config --global user.email
3. 로컬에 커밋 - comimt
4. 원격 저장소에 -push

3단계라 어려워 보이지만 논리적으로 생각하면 어렵지 않아요.

변경사항 모으기 -> 로컬에 변경 정보 반영하기 -> 원격에 변경 사항 반영하기

음... 흐름이 명확해서 까먹을 일 없어보이네요.

### 4.1 수정 사항 모으기 - add
모든 변경 사항을 모아봅시다.
```bash
git add *
```

### 4.2 본인 입력 - git config --global user.email
누가 사용하는지 입력해주세요.
```bash
$ git config --global user.email "여러분이메일@gmail.com"
```

### 4.3 로컬에 커밋 - comimt
로컬에 변경 정보를 커밋합니다.
```bash
$ git commit -m "파일 정리"
[master 64ee957] 파일 정리
 5 files changed, 50 deletions(-)
 create mode 100644 _img/logo.png
 create mode 100644 _img/logo.psd
 create mode 100644 _img/logo_short.png
 create mode 100644 _img/logo_short.psd
 delete mode 100644 _posts/about.md
```

### 4.4 원격 저장소에 -push
드디어 원격 저장소에 변경 사항을 반영합니다.
```bash
$ git push origin master
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 462 bytes | 231.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/ChoiChaJang/choichajang.github.io
   1acc8c6..64ee957  master -> master
```
이로서 간단히 변경 사항 반영하는 방법을 살펴보았습니다.

참고로 깃허브 사용 명령은 다음 포스팅에 아주 잘 정리가 되어 있네요.
(세상에는 훌륭한 분이 참 많아요)

- https://rogerdudler.github.io/git-guide/index.ko.html

## 5.팁 (로컬과 원격 수정 사항이 쫑날 때)
쫑나면 무조건 
1. 로컬 변경을 로컬에
2. 그후 로컬 변경을 원격에
반영해야 합니다.

### 5.1 로컬 변경 -> 로컬
```bash
$ git pull
```

### 5.2 로컬 변경 -> 원격
```bash
$ git push origin master
```
