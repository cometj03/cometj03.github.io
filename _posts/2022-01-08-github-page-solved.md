---
title: Jekyll Github Page - "Automatic build, All jobs have failed" 해결
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-09 19:26:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [minimal mistakes, jekyll]
---

앞으로 `minimal mistakes` 태그에 내가 겪었던 실수나 오류들을 해결한 것을 기록할 예정인데, 오늘은 그 첫 번째 포스팅으로 Jekyll 블로그를 Github Page로 배포하다가 겪은 빌드 실패를 공유하려고 한다.

## Minimal Mistake

![Desktop View](/assets/img/posts/20220108/example0.png){: width="400" height="400" }
_깃허브에게서 받은 이메일_

본론으로 들어가서, Jekyll 설정을 이것저것 하다가 레포에 푸시했는데 빌드에 실패했다며 이런 이메일을 받았다. 나는 같은 현상을 맨 처음 블로그 세팅할 때와 [메인 레포](https://github.com/cotes2020/jekyll-theme-chirpy)와 병합할 때 두 번 겪었다.

![Desktop View](/assets/img/posts/20220108/example1.png){: width="972" height="589" }
_확대 하려면 클릭_

들어가보면 이런 화면이 뜨는데, `Error: The process '~~' failed with exit code 16`라는 에러 문구를 볼 수 있었다.

## Solution

나의 경우엔 `Gemfile.lock`에 입력된 버전이 맞지 않아서 생긴 문제 같다.

그냥 콘솔에 둘 중 하나를 실행한 후 커밋해서 올리면 문제는 간단하게 해결됐다.

```console
$ bundle
$ bundle install
```
