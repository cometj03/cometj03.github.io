---
title: '(해결) Github Actions Error - "Process completed with exit code 1."'
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-10 20:30:00 +0900 # for Korea (UTC+9)
categories: [Ridiculous Mistakes, Github]
tags: [github actions]
sitemap:
  priority: 0.8
---

![Desktop View](/assets/posts/20220109/example2-1.png){: width="500" height="500" }
_삽질의 흔적들..._

## Ridiculous Mistake

![Desktop View](/assets/posts/20220109/example2-2.png){: width="972" height="589" }
_Error: Process completed with exit code 1_

깃허브는 내가 [앞 포스트](https://cometj03.github.io/posts/github-actions-process-failed-exitcode16/)를 올리자마자 새로운 오류를 선사해주었다. 그 내용은 바로.. `Error: Process completed with exit code 1`

## Solution

```diff
---
- title: Github Actions Error - "The process failed with exit code 16" 해결
+ title: "Github Actions Error - \"The process failed with exit code 16\" 해결"
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
...
---
```

나는 이런 방법으로 해결했다.

삽질을 좀 하긴 했지만 마크다운의 글 설정 부분에서 오류가 있었던 모양이다. `---` 으로 감싸져있는 부분은 YAML 문법으로 작성되는데, YAML은 따옴표가 없으면 문자열로 인식하는 특징이 있다. 그래서 명시적으로 따옴표를 붙이고 이스케이프 문자를 사용하거나, 쌍따옴표(`"`)와 따옴표(`'`)의 조합으로 해결할 수 있다.

> 물론 나와 원인이 다를 수도 있겠지만, 제목 등 글 설정 부분에서 YAML문법을 어긴 것이 있는지 확인하는 게 좋을 것 같다.

참고 자료: <https://m-falcon.tistory.com/458>
