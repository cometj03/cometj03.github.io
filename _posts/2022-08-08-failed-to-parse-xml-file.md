---
title: "Android Build Failed - Failed to parse XML file '.../activity_main.xml'"
author: jhs
date: 2022-08-08 21:49:00 +0900 # for Korea (UTC+9)
categories: [Ridiculous Error, Android Error]
tags: [dataBinding]
sitemap:
  priority: 0.8
---

앱 개발 하던 중 액티비티 xml을 만들고 data binding을 사용하기 위해 루트 레이아웃을 `<layout>`으로 바꾸었더니 아래의 오류 메시지와 함께 오류가 발생했다.

# 오류 메시지

```error
FAILURE: Build completed with 2 failures.

1: Task failed with an exception.
-----------
* What went wrong:
Execution failed for task ':app:mergeDebugResources'.
> A failure occurred while executing com.android.build.gradle.internal.res.ResourceCompilerRunnable
   > Resource compilation failed (Failed to compile resource file: D:\Projects\Android\TR_cafe_order_app\app\build\intermediates\incremental\debug\mergeDebugResources\stripped.dir\layout\activity_main.xml: . Cause: com.ctc.wstx.exc.WstxParsingException: Duplicate attribute '{http://schemas.android.com/apk/res/android}layout_width'.
      at [row,col {unknown-source}]: [18,346]). Check logs for more details.

==============================================================================

2: Task failed with an exception.
-----------
* What went wrong:
Execution failed for task ':app:parseDebugLocalResources'.
> A failure occurred while executing com.android.build.gradle.internal.res.ParseLibraryResourcesTask$ParseResourcesRunnable
   > Failed to parse XML file 'D:\Projects\Android\TR_cafe_order_app\app\build\intermediates\packaged_res\debug\layout\activity_main.xml'

```

# Solve

2번 오류 메시지에 힌트가 있었다. `Failed to parse XML file '.../activity_main.xml'`

정확히 어디서 문제가 생겼는지 알기 위해서는 다른 오류 메시지도 함께 읽어봐야 한다.

나의 경우에는 루트 레이아웃을 constraintLayout에서 layout으로 바꾸는 과정에서 `layout_wigth`와 `layout_height` 속성을 지우지 않은 것이 문제가 됐었다.

```diff
<layout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
-    android:layout_width="match_parent"
-    android:layout_height="match_parent"
    tools:context=".ui.MainActivity">
```

layout 태그에 위의 두 속성이 없다는 것을 처음 알았기 때문에 바보같지만 유익한 오류였다고 생각한다. ㅎㅎ..
