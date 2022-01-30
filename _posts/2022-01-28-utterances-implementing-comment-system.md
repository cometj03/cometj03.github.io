---
title: Utterances - Implementing Jekyll Blog Comment System / 블로그 댓글 기능 구현하기
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-28 18:35:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [customize, jekyll]
sitemap:
  priority: 0.8
---

댓글 플러그인 중 가장 많이 쓰고 표준이라고 생각되는 것은 [Disqus](https://disqus.com/)인 것 같다. 나도 처음에는 Disqus를 사용하려고 했지만 첫인상이 조금 조잡하다는 느낌을 받아서 망설이고 있던 참이었다. 그러다가 시간이 지나면 광고까지 붙는다는 사실을 알게 된 후 Disqus는 더이상 내 안중에서 사라졌다.

### Utterances의 장점?

[Utterances](https://utteranc.es/)는 Disqus처럼 댓글기능을 추가할 수 있는 플러그인 중 하나이다. `Utterances`의 특징들은 나에게 매력적으로 다가왔고, 여러 장점들 때문에 블로그의 댓글 플러그인으로 선택하게 되었다.

- 심플한 디자인

  사실 나는 간단한 **댓글 기능**을 추가하고 싶은 것이었기 때문에 글을 작성할 수 있는 텍스트박스와 댓글을 등록하는 버튼, 이 두 개만 있으면 충분했다. 그런 점에서 `Utterances`의 디자인은 현실적이지 않았던 내 바람에 적합할 정도로 간단하다.

- 댓글 등록 방식

- 오픈소스

  https://github.com/utterance

내가 `Utterances`를 선택한 이유는 디자인이 직관적이고, 무엇보다 댓글이 Github 저장소의 Issue로 등록되는 방식이 획기적이라고 생각했기 때문이다. 또한 댓글들이 Issues 탭에서 볼 수 있기 때문에 관리하기에도 용이할 것 같다.
