---
title: Kotlin - Scope Function (run, with, apply, also, let)
author:
  name: Jung Hae Sung
  link: https://github.com/cometj03
date: 2022-01-17 17:16:00 +0900 # for Korea (UTC+9)
categories: [Development, Reference]
tags: [kotlin]
sitemap:
  priority: 0.8
---

## run

```kotlin
public inline fun <T, R> T.run(block: T.() -> R): R {
    return block()
}
```

## with

```kotlin
public inline fun <T, R> with(receiver: T, block: T.() -> R): R {
    return receiver.block()
}
```

## apply

```kotlin
public inline fun <T> T.apply(block: T.() -> Unit): T {
    block()
    return this
}
```

## also

```kotlin
public inline fun <T> T.also(block: (T) -> Unit): T {
    block(this)
    return this
}
```

## let

```kotlin
public inline fun <T, R> T.let(block: (T) -> R): R {
    return block(this)
}
```

Scope Function의 응용 예시는 [여기](https://kotlinlang.org/docs/scope-functions.html)에서 자세하게 확인할 수 있다.
