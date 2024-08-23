---
title: 깃 블로그 만들기(윈도우)
date: 2024-08-16 19:32:00 +0900
categories: [블로그 제작기]
tags: [블로그]
description: 블로그를 만들어보자
media_subpath:
---

# 시작하기 전에

gitHub 아이디가 있어야 하고 사용할 줄 알아야 한다<br>
현재의 이 글은 jekyll과 ruby가 설치가 되어있다고 가정하고 시작하는 것이다<br>
글쓴이는 예비군으로 인하여 지금 매우매우 귀찮기 떄문에 그 설명을 지금은 안하고 나중에 하려한다

### 1.레포지토리를 만들고 테마를 가지고 오기

우선 깃허브에 들어가서 새로운 레포지토리를 만든다
![이미지](/assets/img/madeblog/1.JPG)

레포지토리에 이름은

```bash
(본인 닉네임).github.io
```

라고 작성을 해주며 그림처럼 체크를 하고 만든다

깃을 만들고 본인이 원하는 폴더에 들어가 clone을 해준다

이후에 깃 허브 블로그를 만들 때 대부분 테마를 가지고와서 본인의 입맛대로 꾸미기 시작한다

[https://jekyllthemes.io/free](https://jekyllthemes.io/free)

대부분의 사람들이 위에 있는 곳에서 테마를 다운받아 사용한다

그치만 나는 [https://github.com/cotes2020/chirpy-starter](https://github.com/cotes2020/chirpy-starter) 요걸로 했다 블로그를 돌아다니다보니<br>
이 테마 관련 게시물들이 많았던것 같다

해당 깃 허브에 들어가서 zip 파일을 다운받고 아까 클론받은 (본인 닉네임).githyb.io에 전부 복사 붙여넣기를 한다.

그리고

```bash
bundle exec jekyll serve
```

해당 경로에 위 명령어를 실행하면 [localhost:4000](https://localhost:4000) 주소에 켜지는것을 알 수 있다

### <span style ="color: red;">주의할 점</span>

위와 같이 진행하다보면은 오류가 하나 생길 수도 있다

```bash
Dependency Error: Yikes! It looks like you don't have tzinfo or one of its dependencies installed.
In order to use Jekyll as currently configured, you'll need to install this gem.
If you've run Jekyll with bundle exec, ensure that you have included the tzinfo gem in your Gemfile as well.
The full error message from Ruby is: 'cannot load such file -- tzinfo' If you run into trouble,
you can find helpful resources at https://jekyllrb.com/help/!
jekyll 4.3.3 | Error:  tzinfo
```

대충 이런 오류인데 폴더내에 파일이 없다라는 이야기다

우리 블로그 폴더에 Gemfile이라는 아이가 있다 그 아이폴더를 열어서

```bash
gem "tzinfo"
gem "tzinfo-data"
```

이걸 추가해준다 그리고 블로그 폴더가 있는 cmd 창에서

```bash
bundle
```

이라고 쳐주면 뭔가를 막 다운받는데 위에 파일을 다운받는것이다

그리고 혹시모르니깐

```bash
gem uninstall jekyll
gem install jekyll
```

요것도 cmd 창에서 해주자

그러니깐 나는 해결이 되었다

### 2.자신의 정보로 수정하기

정상적으로 실행이 된다면 해당정보를 수정해야 하는데

수정하기 위해서는 visual code라는 아이를 사용해서 수정을 해야한다

해당 폴더를 열면 여러가지가 있는데 그중에서 \_config.yml이라는 파일을 찾아야된다

파일을 찾았으면

```yml
// 블로그 언어 설정
lang: ko-KR

// 블로그 시간 설정
timezone: Asia/Seoul

// 블로그 연동 url 설정
url: "https://본인닉네임.github.io"

// 프로필 설정
avatar: 프로필 파일경로

//사이드바 블로그 상태 메시지
tagline:

// 깃허브 유저이름
github:
  username:

//트위터
twitter:
  username: twitter_username

//본인 이름이랑 이메일
social:

  name:
  email:
  links:

//사이드바 아바타
avatar:

```

등등을 수정해주면된다

다음에는 옆에 사이드 바를 본격적으로 꾸며보자
