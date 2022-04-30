---
# prettier-ignore
title: (해결) Github Actions Error - &quot;Process completed with exit code 1.&quot;
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-10 20:30:00 +0900 # for Korea (UTC+9)
categories: [Ridiculous Error, Github Actions]
tags: [github actions]
sitemap:
  priority: 0.8
---

![Desktop View](/static/img/20220110-1.png){: width="500" height="500" }
_삽질의 흔적들..._

## Ridiculous Error

![Desktop View](/static/img/20220110-2.png){: width="972" height="589" }
_Error: Process completed with exit code 1_

깃허브는 내가 [앞 포스트](https://cometj03.github.io/posts/github-actions-process-failed-exitcode16/)를 올리자마자 새로운 오류를 선사해주었다. 그 내용은 바로.. `Error: Process completed with exit code 1`

## Solution

```diff
---
- title: Github Actions Error - "The process failed with exit code 16" 해결
+ title: Github Actions Error - &quot;The process failed with exit code 16&quot; 해결
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
...
---
```

나는 이런 방법으로 해결했다.

삽질을 좀 하긴 했지만 마크다운의 글 설정 부분에서 오류가 있었던 모양이다. `---` 으로 감싸져있는 부분은 YAML 문법으로 작성되는데, YAML은 따옴표가 없으면 문자열로 인식하는 특징이 있다. 보통 문자열 안에 따옴표를 쓰기 위한 방법으로 이스케이프 문자를 사용하거나, 쌍따옴표(`"`)와 따옴표(`'`)의 조합으로 사용할 수 있다. 그런데 이 방법도 깃허브 페이지를 배포하는 과정에서 오류가 난다.

마침내 내가 찾은 방법은 'HTML 특수문자 코드'를 사용하는 것이다. 예를 들어 큰따옴표(`"`)는 HTML 특수문자 코드로 `&quot;`이다.

> 필자와 원인이 다르다면 제목 등 글 설정 부분에서 YAML 문법을 어긴 것이 있는지 확인하거나, 특수문자는 되도록이면 HTML 특수문자 코드로 바꿔 사용하는 것이 좋을 것 같다.

- YAML 문법 참고: <https://m-falcon.tistory.com/458>

- HTML 특수문자 코드 참고: <https://aneok.tistory.com/86>
