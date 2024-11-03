---
title: "[정수론] #1 How to prove a statement - Direct Proof"
author: jhs
date: 2024-11-03 12:30:00 +0900 # for Korea (UTC+9)
categories: [수학, 정수론]
tags: []
math: true
---

> 이 글은 정수론 수업을 들으며 공부한 내용을 바탕으로 필자의 해석을 추가하여 정리한 글입니다. 글의 흐름은 교수님께서 제작하신 수업 자료의 것을 따라가고 있습니다.

첫 번째와 두 번째 챕터에서는 정수론을 공부하기 전 필수로 알고 있어야 하는 사전 지식(preliminary)들을 정리하고 있습니다. 꼭 정수론이 아니더라도 모든 수학 분야에 적용된다고 봐도 될 것 같습니다.
그럼 그 첫 번째 챕터인 How to prove a statement, 명제의 참/거짓을 증명하는 방법에 대해 알아보겠습니다.

# Direct Proof
명제를 증명하는 방법은 크게 직접(direct) 증명하는 방법과 간접적으로(indirect) 증명하는 방법으로 나눌 수 있습니다.

Direct proof는 conditional statement를 증명할 때 유용합니다.
conditional statement는 "P이면 Q이다", "If P then Q", "P implies Q", "P $\Rightarrow$ Q"로 표현되는 명제를 말합니다. 여기서 P는 hypothesis(가설, 가정), Q는 conclusion(결론)이라고 합니다.

그럼 다음 예시를 보면서 감을 잡아보도록 하죠.

## Example 1

> **Prove:** Let $m,n$ be integers. If both $m$ and $n$ are odd, then $mn$ is odd.
{: .prompt-tip }

이 명제는 두 홀수의 곱이 홀수라고 주장하고 있습니다. 우선 증명하기 전에 이 명제는 참일까요, 거짓일까요? 그렇게 생각한 이유는 무엇인가요? 여기서 말하는 '이유'는 꼭 합리적일 필요는 없습니다. 아직 증명을 하기 전이니까요.

참고로 "Let $m,n$ be integers."라는 문장은 grand assumption(대전제)라고 합니다. 명제를 변형할 때(역, 대우 등) 대전제는 바뀌지 않습니다.

이 명제는 홀수의 정의만 알고 있다면 증명할 수 있습니다. 홀수의 정의는 적절한 정수 $k$에 대해 $2k+1$로 표현할 수 있는 수입니다. 이것을 수학적으로 $n = 2k+1 \textbf{ for some } k \in \mathbb{Z}$와 같이 표현합니다. (참고로 '$k \in \mathbb{Z}$'는 'k in z'로 발음하면 됩니다. 앞으로 새로운 표현이 나올 때마다 읽는 방법도 설명하겠습니다.)

먼저 우리에게 '주어진 것'과 '보일 것'을 정리합니다. (두 번째 문장은 첫 번째 문장을 수학이라는 언어로 표현했을 뿐 같은 의미입니다. 여기서는 저렇게 표현할 수 있구나 하고 넘어가도 됩니다.)
- 주어진 것(Given)
	- 정수 $m, n$이 홀수
	- $m,n \in \mathbb{Z}$, $m = 2k+1 \textbf{ for some } k \in \mathbb{Z}$ and $n = 2l+1 \textbf{ for some } l \in \mathbb{Z}$
- 보일 것(will show)
	- $mn$이 홀수
	- $mn = 2r+1 \textbf{ for some } r \in \mathbb{Z}$

증명은 간단합니다. 주어진 것을 가지고 결론(보일 것)에 도달할 수 있는지를 보이면 됩니다.

$$
\begin{split}
mn &= (2k+1)(2l+1) \\ &= 4kl+2k+2l+1 \\ &= 2(2kl+k+l) + 1 \\ &= 2r+1
\end{split}
$$

이렇게 끝내도 되지만, '보일 것'의 조건을 잘 보면 $r$이 정수라는 것이 있기 때문에 그것까지 확인을 시켜줘야 합니다.

$$
\textbf{Since } k,l \in \mathbb{Z}, r=2kl+k+l \in \mathbb{Z}
$$

정수 집합은 덧셈과 곱셈에 대해 닫혀있기 때문에 정수 $k, l$ 들의 곱셈과 덧셈으로 나온 결과인  $2kl+k+l$ 또한 정수라는 의미를 내포하고 있습니다. (정수 집합이 덧셈과 곱셈에 대해 닫혀있다는 의미는 정수끼리 덧셈을 하거나 곱셈을 해도 그 결과가 정수라는 의미입니다.)

이렇게 홀수(odd)의 정의만 알고 있다면 "If both $m$ and $n$ are odd, then $mn$ is odd."가 참이라는 것을 증명할 수 있습니다. 이와 같이 direct proof는 정의를 이용하여 직접 증명하는 것이 대표적입니다.

## Example 2

> **Prove:** For every integer $n$, the integer $n^2+n$ is even.
{: .prompt-tip }

이번 명제는 "모든 정수 $n$"에 대해 저렇게 계산한 값이 항상 짝수라고 주장하고 있습니다. 정말 그럴까요? $n$이 1이라면 계산한 결과는 2(=$1^2 + 1$), 2라면 6(=$2^2+2$), 3이라면 12(=$3^2+3$). 몇 개 넣어보니 맞는 말 같긴 한데, 숫자와 같이 무한한 대상에 대해서는 일일이 넣어 확인하는 것이 불가능합니다. 우리의 삶은 유한하니까요.

대신 "**모든 정수는 홀수 또는 짝수**"라는 한 가지 당연한 사실을 떠올려봅시다. 이 사실이 참이라면 우리는 $n$이 홀수일 때와 짝수일 때의 경우로 나눠 생각할 수 있고, 이것은 모든 정수를 넣어보는 것보다 쉽습니다. 보통 이렇게 자명한 사실은 따로 증명하지 않아도 됩니다.

수학이 재미있는 이유 중 하나는 바로 이렇게 당연하고 별 볼일 없어보이는 것에도 의미가 숨어있고, 그것을 새로운 시각으로 관찰하는 데에 있는 것 같습니다.

이제 Example 1에서 했던 것과 같이 주어진 것과 보일 것을 적습니다.

- 주어진 것(Given)
	- $n$은 정수. 즉 n은 홀수 또는 짝수
	- $n = 2k$ or $n=2k+1 \textbf{ for some } k \in \mathbb{Z}$
- 보일 것(will show)
	- $n^2+n$이 짝수
	- $n^2+n=2r \textbf{ for some } r \in \mathbb{Z}$ 

Case 1)
: If $n$ is $2k$, then $n^2+n=(2k)^2+(2k)=2(2k^2+k)$

Case 2)
: If $n$ is $2k+1$, then $n^2+n=(2k+1)^2+(2k+1)=2(2k^2+3k+1)$

Since $k \in \mathbb{Z}$, $r=2k^2+k \in \mathbb{Z}$ or $r=2k^2+3k+1 \in \mathbb{Z}$

이렇게 $n$이 $2k$일 때, $n$이 $2k+1$일 때 각각 계산해서 모든 경우에 대해 $n^2+n$으로 계산한 결과가 짝수라는 것을 증명했습니다.