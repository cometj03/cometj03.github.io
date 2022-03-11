---
title: My Future Development Study Plan / 나의 앞으로의 개발 공부 계획
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-30 00:05:00 +0900 # for Korea (UTC+9)
categories: [Chatting, About Me]
tags: [plan, development]
sitemap:
  priority: 0.8
---

### (feat. Utterances 테마 동적으로 변경하는 방법)

Disqus는 가장 많은 사람들에게 사용되고 있는 댓글 플러그인 중 하나이다. 나도 처음에는 블로그 댓글로 그나마 친숙했던 Disqus를 고려하고 있었다. 하지만 디자인이 내 마음에 들지 않았고, 게다가 시간이 지나면 광고가 붙는다는 점 때문에 결국 고려대상에서 제외했다. 그렇게 다른 대안을 찾던 중 Utterances라는 플러그인이 내 눈길을 사로잡았다.

# Utterances?

Utterances는 Disqus처럼 댓글 플러그인 중 하나이다. 하지만 Disqus와는 구별되는 독특한 특징이 있고, 이는 내가 Utterances를 선택한 이유이기도 하다. 그 이유들을 정리하면 다음과 같다.

[오픈소스](https://github.com/utterance)

댓글 등록 방식
: Utterances는 깃허브 저장소의 Issues 기능을 활용해 댓글을 구현한다. 이러한 방식 덕분에 Markdown 문법을 사용해 댓글을 달 수 있고, 텍스트 스타일을 변경하거나 이미지 첨부 등이 간단하게 해결된다.

심플한 디자인과 기능
: 처음 접하는 사람도 한번에 사용할 수 있을 정도로 간단한 디자인과 기능을 제공한다.

# 내 블로그에 적용해보자

여기에 나와있는 절차들은 [공식 사이트](https://utteranc.es/) 또는 기타 블로그에서 가져온 정보들로 구성되어 있다.

## 1. Github App 설치

![utterances github app installation](/assets/posts/20220221/example1.png)
_나는 이미 설치를 한 상태여서 'Configure' 버튼이 보인다._

[Utterances 설치 사이트](https://github.com/apps/utterances)에 접속한 후 Install 버튼을 눌러 댓글 Issue가 저장될 “public” 저장소를 선택한다. 새로 만든 빈 저장소를 선택하거나, 필자처럼 깃허브 블로그 저장소가 public이라면 그 저장소를 선택해도 좋다.

포크를 찍은 저장소라면 Issues 탭이 보이지 않는데, Settings > Features의 Issues를 체크해주면 정상적으로 보인다. (저장소 == repository)

## 2. 설정

[공식 사이트](https://utteranc.es/)에 몇가지를 입력하면 그것에 맞는 스크립트 태그가 생성되고, 우리는 그 코드를 활용할 것이다.

![](/assets/posts/20220221/example2.png)

2-1
: 연결할 저장소 입력. ‘<깃허브 닉네임>/<저장소 이름>’ 형식으로 채워넣는다.

![](/assets/posts/20220221/example3.png)

2-2
: 나는 댓글 매핑 방식을 기본 설정값인 page pathname으로 했다. Issue 제목을 포스트 파일 이름으로 설정하겠다는 뜻이다.

2-3
: Issue label은 Issue 제목에 특정한 문자열을 넣어서 Utterances가 등록한 것인지 식별하고 싶을 때 사용하는 것인데, 나는 딱히 필요성을 못 느껴서 빈칸으로 두었다.

2-4
: 테마는 마음에 드는 걸로 선택하면 된다. 나는 Github Dark를 선택했다.

## 3. 블로그에 추가

![generated script](/assets/posts/20220221/example4.png)

위의 절차를 모두 끝냈다면 사이트 하단에 이러한 스크립트가 생성된다. 이 스크립트를 사용해 Jekyll 블로그에 댓글을 적용하는 방법은 두 가지로, 정적인 방식과 동적인 방식이 있다.

### 3-1. \_layouts/post.html에 추가하기 (정적)

{: file='\_layouts/post.html'}

```html
<!-- _layouts/post.html 부분 생략 -->

<script
  src="https://utteranc.es/client.js"
  repo="cometj03/cometj03.github.io"
  issue-term="pathname"
  theme="github-dark"
  crossorigin="anonymous"
  async
></script>
```

블로그 소스 폴더의 `_layouts/post.html` 파일 맨 하단에 위 스크립트를 복사해 붙여넣으면 된다.
이 방법이 가장 기본적인 방법이지만, 테마를 바꾸지는 못한다는 단점이 있다.

나는 이 단점을 해결하기 위해 다른 방법을 사용했다.

### 3-2. Liquid와 자바스크립트 활용하기 (동적)

Liquid는 HTML에 직접 삽입된 변수, 조건문 등이 순수 HTML로 해석되는 템플릿 언어이다.
또한 Jekyll은 Liquid를 지원하기 때문에 이를 잘 활용하면 더 효율적인 사이트를 만들 수 있다.

{: file='\_config.yml'}

```yaml
comments:
  active: utterances # The global switch for posts comments, e.g., 'disqus'.  Keep it empty means disable
  utterances:
    repo: cometj03/cometj03.github.io # <gh-username>/<repo>
    issue_term: pathname # < url | pathname | title | ...>
```

사실 내가 사용하고 있는 블로그는 Utterances를 구현하기 위한 Liquid와 자바스크립트가 이미 다 준비되어 있었기 때문에 직접 구현할 일은 없었다. 단지 `_config.yml` 파일의 `comments` 부분을 위와 같이 적절하게 채우면 구현이 완료된다.

이미 준비되어 있지 않은 블로그를 사용하고 있다면 [이 코드](https://github.com/cometj03/cometj03.github.io/blob/master/_includes/comments/utterances.html)를 복사해서 적절한 곳에 넣으면 될 것이다.

## 마무리

드디어 나의 블로그에 댓글 기능을 추가했다! 이제 `bundle exec jekyll s` 를 실행해 댓글이 정상적으로 추가가 됐는지 확인하고, 3-2번 방법을 시도했다면 테마가 잘 바뀌는지도 테스트해보자.

잘 되지 않는 것이 있다면 댓글로 질문 부탁드리고, 잘못된 부분은 지적해주시면 감사하겠습니다.
