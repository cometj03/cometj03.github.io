---
title: Precautions When Writing a Github Blog / 깃허브 블로그 작성할 때 주의사항
author:
  name: { { site.social.name } }
  link: https://github.com/cometj03
date: 2022-03-29 21:43:00 +0900 # for Korea (UTC+9)
categories: [Ridiculous Error, Github]
tags: [github actions, jekyll]
sitemap:
  priority: 0.8
---

그동안 깃허브 블로그를 완성하고 글을 올리는 과정에서 정말 다양한 요류들을 겪었다. 최근에는 블로그 댓글 기능 구현과 관련된 글을 작성하고 한동안 같은 오류로 블로그 사이트가 제대로 퍼블리싱되지 않았던 적이 있었다. 그 오류의 원인은 알고보니 너무 간단했다. 내가 특정 형식을 나타내기 위해 "&lt;깃허브 닉네임&gt;/&lt;저장소 이름&gt;"으로 쓴 곳에서 `<깃허브 닉네임>`이라는 HTML 태그가 존재하지 않는다고 드러누운 것이었다. 로컬로 빌드할 땐 문제없이 잘만 되더니..

아무튼 이런 어이없는 오류들을 겪다보니 앞으로도 의도치 않게 많이 접할 것 같다는 생각이 든다. 그래서 앞으로 깃허브 블로그와 관련된 오류는 '깃허브 블로그 작성할 때 주의사항'이라는 제목의 글에 모아두려고 한다. 원래는 [오류 관련 카테고리](https://cometj03.github.io/categories/ridiculous-error/)를 두고 그곳에 글들을 담아두려고 했는데 지금처럼 하다가는 블로그 관련 오류 글만 잔뜩 있고 정작 중요한 글이 묻힐 것 같아서 말이다.

이들은 앞서 올렸던 두 포스팅이다.

[Github Actions Error - The process failed with exit code 16. 해결](https://cometj03.github.io/posts/github-actions-solved/)

[Github Actions Error - Process completed with exit code 1. 해결](https://cometj03.github.io/posts/github-actions-solved2/)
