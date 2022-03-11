---
title: Utterances - Applying The Jekyll Blog Comment Feature / 블로그 댓글 적용하기
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-02-21 14:35:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [customize, jekyll]
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
