---
title: Jekyll Youtube Plugin 적용하기
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-08 18:31:00 +0900 # for Korea (UTC+9)
categories: [Development, Github]
tags: [jekyll plugins, jekyll]
---

<https://github.com/dommmel/jekyll-youtube>

나는 공식 문서에도 있는 이 링크를 참고했다.

여기에도 친절하게 잘 설명되어 있어서 더 적을 내용은 없지만,
내가 하면서 조금이라도 헤맸던 부분들에 대해 중간중간 첨언하려고 한다.

## Jekyll 플러그인 적용하기

### 설치

#### 1. `Gemfile`에 코드 추가하기

{: file='Gemfile'}

```ruby
group :jekyll_plugins do
  gem "jekyll-youtube"
end
```

> **Note**: `:jekyll_plugins`가 `Gemfile`에 없다면 빈 공간에 코드를 추가하자. 있으면 `gem "jekyll-youtube"`부분만 추가하면 된다.

<br>

#### 2. 콘솔 실행하기

```console
$ bundle
$ gem install jekyll-youtube
```

> **Note**: 둘 중 하나만 실행해도 된다고 한다.

<br>

#### 3. `_config.yml`에 코드 추가하기

{: file='\_config.yml'}

```yaml
plugins: [jekyll-youtube]
```

> **Note**: []는 리스트라서 여러 개라면 `,`를 사용하여 추가한다.

### 사용법

직접 링크 입력

```text
{ % youtube "https://www.youtube.com/watch?v=gset79KMmt0" % }
```

또는 [`front matter`](https://jekyllrb.com/docs/front-matter/) 변수 사용

```text
---
youtubeurl: https://www.youtube.com/watch?v=gset79KMmt0
---
{ % youtube page.youtubeurl % }
```

> 유튜브 링크는 온전한 링크만 사용이 가능한 것 같다. 공유 링크는 작동을 안 한다.

### 결과

{% youtube "https://www.youtube.com/watch?v=gset79KMmt0" %}
<br>

> 나의 경우처럼 블로그 미리보기로 보면 동영상을 재생할 수 없다고 뜰 수도 있는데, 그냥 커밋, 푸시한 다음 몇 분 기다리면 해결되는 것 같았다.
