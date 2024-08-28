---
title: 깃 블로그 만들기 - 사이드바 꾸미기 (윈도우)
date: 2024-08-16 19:33:00 +0900
categories: [블로그 제작기]
tags: [블로그]
description: 사이드바를 꾸며보자
media_subpath:
---

### 1.아바타 바꾸기

> 우선 큼지막하게 눈에 보이는것을 바꿔보자 사진 같은경우에는 자기가 원하는 사진을 가지고 오면 되는데

```yml
//사이드바 아바타 (사진)
avatar:

```

> 이전 포스트에도 있는 이 부분을 수정해 주면된다 어렵게 생각하기 싫어서 나는 아바타이미지는 그냥 폴더안에 넣었다
> (어짜피 바꿀일이 없고 하나만 들어가니까)

```yml
//사이드바 아바타 (사진)
avatar: 이미지이름.확장자

```

> 이미지를 폴더에 넣었으면 yml파일에 들어가서 설정해주면 된다

### 2.배경바꾸기

> 이번에는 배경을 바꾸어보자 배경을 꾸미기 위해서는 \_saas폴더가 필요한데
> [https://github.com/cotes2020/jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)

> 링크에 있는 깃허브에서 zip파일을 다운받은후 압축을 풀고 안에있는 \_saas파일을 전부 복사해서 우리 폴더에 붙여넣는다

> 붙여넣었으면 visual code에서 \_sass파일에 commons.scss라는 파일에 들어가서 ctrl + f 키를 누른다

> 누르게 되면 검색창이 하나 뜰것인데 이때 #sidebar를 검색해주면

```scss
#sidebar {
  @include pl-pr(0);

  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  overflow-y: auto;
  width: $sidebar-width;
  z-index: 99;
  background: url(요기에 이미지 파일);
  background-size: cover;
  border-right: 1px solid var(--sidebar-border-color);

  /* Hide scrollbar for IE, Edge and Firefox */
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */

  /* Hide scrollbar for Chrome, Safari and Opera */
  &::-webkit-scrollbar {
    display: none;
  }

```

> 이 친구가 나오게 된다 이 친구안에 Url에 본인이 원하는 이미지의 경로를 넣어주면된다

> 만약 원하는 그림이 반복적으로 나오게 된다면 height 값을 수정해보면 된다

### 3.글씨 색 바꾸기

> 이제는 글씨의 색을 바꾸어 볼것이다

> 우선 제일 큰 제목을 바꾸어 보자

> 아까처럼 commons.scss라는 파일에 들어가서

```scss
.site-title {
  font-family: inherit;
  font-weight: 900;
  font-size: 1.75rem;
  line-height: 1.2;
  letter-spacing: 0.25px;
  margin-top: 1.25rem;
  margin-bottom: 0.5rem;

  a {
    @extend %clickable-transition;
    @extend %sidebar-link-hover;

    color: ;
  }
}
```

> site-title를 찾는다 이 아이에 색깔을 수정해 주면 큰 제목의 색깔이 달라진다

> 다음은 그 밑에 있는 글자의 색을 바꾸어 보자 위와 똑같은 파일에서 color의 색을 수정해주면 된다

```scss
.site-subtitle {
  font-size: 95%;
  color: ;
  margin-top: 0.25rem;
  word-spacing: 1px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
```

> 아 그리고 아바타 밑에 있는 큰 글씨는 다른 글씨와는 다르게 마우스를 올리면 색깔이 변하는데

> 이 색깔도 수정할 수 있다 이 친구 또한 같은 파일에서 수정하면 된다

```scss
%sidebar-link-hover {
  &:hover {
    color: white;
  }
}
```

> 마지막으로 밑에 글씨의 메뉴의 글씨를 수정해보자 이 친구는 다른 친구와는 다르게 module.css에서 수정을 해야한다

```scss
%sidebar-links {
  color: white;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
```

> 이렇게 사이드바를 적당히 꾸며 보았다
