---
title: "[정수론] #1 How to prove a statement - Indirect Proof"
author: jhs
date: 2024-11-03 18:00:00 +0900 # for Korea (UTC+9)
categories: [수학, 정수론]
tags: []
math: true
---

[이전 글](/posts/number-theory1-1)에 이어 이번 글에서는 명제를 간접적으로 증명하는 Indirect proof 두 가지에 대해 소개합니다.

# Indirect Proof: by Contradiction
간접적으로 증명하는 방법은 두 가지로 나눌 수 있는데 그 중 하나가 모순(contradiction)을 이용한 방법입니다. 

"Assume P, suppose ~Q": 즉 "P라고 했을 때 Q가 아니라고 한다면 모순이 발생할걸?"이라는 논리로 진행됩니다.

모순을 이용한 방법은 주로 conditional statement가 아닌 명제를 증명할 때 유용합니다. P는 보통 grand assumption(대전제)이거나 Q의 특성이나 정의라서 생략할 수 있기 때문입니다.

## Example 1
> The characteristic of Dr. Bean is that if she arrives in the morning at the Math department, she takes her mug from the department office and take a cup of coffee, and she is never without her coffee until she goes home in the evening.
> 
> **Prove:** Dr. Bean has not arrived yet.
{: .prompt-tip }

Dr. Bean은 항상 부서에 도착하면 사무실에서 그녀의 머그를 꺼내오고, 집에 갈 때까지 머그와 함께 있는다고 합니다. Dr. Bean이 아직 부서에 도착하지 않았다는 것을 어떻게 증명할 수 있을까요? (글에 포함되지는 않았지만 그녀의 머그가 아직 사무실에 있다고 가정합니다)

**Suppose not**: 
: Dr. Bean이 도착했다고 해봅시다.

도착했다면 머그를 들고 제자리로 갔을테니 사무실에 머그가 없어야 하는데 그녀의 머그가 아직 사무실에 있습니다. 이것은 모순(Dr. Bean의 특성에 어긋남)이므로 Dr. Bean은 아직 도착하지 않았다고 할 수 있습니다.

## Example 2
> **Prove:** There is no smallest positive rational number.
{: .prompt-tip }

0보다 큰 유리수 중에서 가장 작은 숫자는 무엇일까요? 아쉽지만 실제로 그러한 숫자는 존재하지 않습니다. 만약 그러한 숫자가 존재하고 그것을 $x$라고 합시다. 그런데 $x/2$는 $x$보다 작기 때문에 $x$는 가장 작은 값이 아니게 되므로 모순이 발생합니다. 이 말을 이해했다면 조금 더 엄밀한 증명도 어렵지 않습니다.

모든 것은 정의를 확실히 알고 있는 것에서 시작합니다. 유리수의 정의를 떠올려봅시다. 유리수는 정수를 이용하여 정의됩니다: $m,n$이 정수이고 $n \ne 0$일 때 $m \over n$으로 나타낼 수 있는 수를 말합니다.

이제 위 명제를 부정하여 모순을 이끌어내봅시다.

Proof: 
: Suppose not.
: Let $q$ be the smallest positive rational number.
: So, $q > 0$ and $q = {m\over n},\ n\ne 0,\ \textbf{ for some } m,n \in \mathbb{Z}$
: But, ${q\over 2} = {m \over 2n}$ is such that ${q\over 2} > 0$ and $q\over 2$ is a rational number (because $m,2n \in \mathbb{Z},\ 2n \ne 0$) and ${q \over 2} < q$.
: This contradicts the assumption that $q$ is the smallest positive rational number.
: Hence, there is no smallest positive rational number.

## Example 3
> **Prove:** Let $m$ and $n$ be integers. Prove that if $mn$ is odd, then both $m$ and $n$ are odd.
{: .prompt-tip }

Direct proof에서 다루었던 [Example 1](/posts/number-theory1-1/#example-1)의 명제와 비슷해보이지만, 실제로 다른 명제입니다. 앞에서 증명한 것은 $m, n$이 홀수일 때 $mn$이 홀수인 거고 이건 $mn$이 홀수일 때 $m, n$이 둘 다 홀수라는 명제입니다. 둘이 역 관계입니다. 이 명제도 참이라면 저 두 조건은 필요충분조건이 됩니다.

모순을 이용한 증명에서는 결론만 부정합니다. "both $m$ and $n$ are odd"를 부정하면 "either $m$ or $n$ is even"이 됩니다. 둘 중 하나가 짝수라는 얘기죠. 즉 "if $mn$ is odd, then either $m$ or $n$ is even" 이 문장에 모순이 있다는 것을 보임으로써 원래 명제가 참이라는 것을 증명할 수 있습니다.

결론에서 $m$이 짝수인 경우, $n$이 짝수인 경우, $m$과 $n$이 모두 짝수인 경우 총 세 가지 경우를 보아야 합니다. 그런데 거의 비슷한 결과를 굳이 여러 번 보이는 건 귀찮습니다. 이럴 때 "without loss of generality"(일반성을 잃지 않고) 둘 중 짝수인 수를 $m$이라고 둘 수 있습니다. 보통 *WLOG*라는 약자로 사용합니다.

주어진 것(Given)
: $mn$이 홀수
: $mn=2k+1 \textbf{ for some } k \in \mathbb{Z}$ 

가정(suppose)
: $m$ 또는 $n$ 중 적어도 하나는 짝수. *일반성을 잃지 않고*, 둘 중 짝수인 수를 $m$이라 하자
: *WLOG*, let $m$ be the even integer. So, $m=2l \textbf{ for some } l \in \mathbb{Z}$

Proof:
: $m$을 짝수라고 한다면 $mn=(2l)n=2(ln)$이므로 $mn$ 또한 짝수가 됩니다. 이는 $mn$이 홀수라는 가정에 모순됩니다.


# Indirect Proof: by Contrapositive
간접적으로 증명하는 방법 중 두 번째 방법으로 대우(contrapositive)를 이용하는 방법이 있습니다.

즉 "$P \Rightarrow Q$ (P이면 Q이다)"는 논리적으로 그것의 대우인 "$\sim Q \Rightarrow \sim P$ (Q가 아니면 P가 아니다)"와 동치이기 때문에 둘 중 하나가 해결되면 다른 하나도 저절로 해결됩니다. 따라서 둘 중 더 증명하기 쉬운 명제를 증명하겠다는 의미입니다.

## Example 1
> Let $x$ be a positive real number. 
> 
> **Prove:** if $x$ is irrational, then $\sqrt{x}$ is irrational.
{: .prompt-tip }

어떤 수가 무리수인지 증명하는 것은 까다롭습니다. 대신 어떤 수가 유리수인 것을 보이는 것은 상대적으로 간단합니다. 따라서 증명하려는 문장의 대우를 살펴봅시다.

- 원래 문장: $x$가 무리수이면 $\sqrt{x}$가 무리수이다.
- 대우: $\sqrt{x}$가 무리수가 아니면 $x$는 무리수가 아니다.

$x$는 양의 실수라고 했으므로 무리수가 아니라는 것은 유리수라는 의미입니다. 이제 새로운 명제가 생겼으니 direct proof로 증명해보겠습니다. 다른 방법으로 해도 됩니다.

주어진 것(Given)
: $x$는 양의 실수, $\sqrt{x}$가 유리수
: $\sqrt{x} = {m \over n}, \textbf{ for some } m,n \in \mathbb{Z}, n \ne 0$

보일 것(will show)
: $x$가 유리수

Proof: 
: $x>0$이므로 $\sqrt{x}^2=x={m^2 \over n^2}$. 그리고 $m^2,n^2 \in \mathbb{Z}, n^2 \ne 0$. 따라서 $x$ 또한 유리수입니다.

---

이렇게 챕터 1이 끝났습니다. 실제로 수학에서 소개되는 증명들은 모두 [이전 글](/posts/number-theory1-1)에서 소개한 Direct proof와 이 글에서 설명한 Indirect proof에 기반을 두고 있다고 보아도 무방할 것 같습니다.

다음 글에서는 어떤 명제가 모든 자연수에 대해 참인 것을 보이기 위한 수학적 귀납법에 대해 소개하겠습니다.