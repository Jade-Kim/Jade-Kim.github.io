---
title: "로컬 VS Code 에서 Github SSH Key 생성하고 연결하는 방법"
excerpt: "나의 로컬 컴퓨터 VS Code 에서 github 계정으로 커밋, 풀, 푸시 등 remote repo 로 업로드 가능한 작업을 하기 위해 나의 github 계정을 SSH 로 연결하는 방법에 대해 알아보자."
header:
  overlay_color: "#7515F2"
  overlay_filter: rgba(0, 0, 0, 0.5)
categories:
  - Web
tags:
  - 웹개발
---

1. terminal 또는 command 창을 연다.
2. git 설치되어 있는지 확인하기
   `git version`
   내 컴퓨터에 git이 설치되어 있지 않다면 아래 링크에서 다운로드 받아 설치한다. https://git-scm.com/downloads

3. 아래 ssh keygen 생성 명령어를 입력하고 Enter
   xxx@gmail.com 대신에 나의 github 계정 이메일을 입력한다.
   `ssh-keygen -t ed25519 -C “xxx@gmail.com”`

4. ssh keygen 생성 도중에 passphrase 입력하라는 메세지가 뜨면 Enter 를 눌러준다. Enter 를 2번 누르면 아래와 같은 메세지가 뜨면서 SSH 가 생성된다!!!

```
Generating public/private ed25519 key pair.
Enter file in which to save the key (/Users/jade/.ssh/id_ed25519):
Created directory '/Users/jade/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/jade/.ssh/id_ed25519
Your public key has been saved in /Users/jade/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:it/1N/gM6csPaIRhnYVyG/cjVXeUBqCLegYBT36Ec+8 xxx@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
|   . ...   oo..o*|
|    =o....=o. .oo|
|     +o.++o+ o.  |
|      o..+o . o  |
|     . .S..  . . |
|     .o. E . .   |
|    ...o  + +.   |
|     .o. o +.+o  |
|      . .   ==+. |
+----[SHA256]-----+
```

5. 위와 같은 화면이 떴다면 SSH 키 생성이 완료된 것이다. SSH 키 생성이 잘 되었는지, 생성된 키 이름을 확인하는 명령어는 아래와 같다.
   `ls ~/.ssh/`

6. 생성된 키 이름을 넣어서 SSH 키 복사하는 명령어는 아래와 같다.
   `pbcopy < ~/.ssh/키이름.pub`

7. 깃헙 계정에 로그인하기

8. 깃헙 세팅에서 SSH Key 를 생성하고 복사한 키 붙여넣기
   `깃헙 settings - SSH key - create key - 복사한 키 붙여넣기 (Ctrl + V 또는 cmd + V)`

9. github repo 에서 clone 할 프로젝트의 clone SSH 복사하기

10. VS code 열고 git clone 하기
    `git clone git@github.com:유저네임/레포이름.git`
