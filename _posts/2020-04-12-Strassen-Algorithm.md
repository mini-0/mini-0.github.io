---
layout: single
title: "Strassen Algorithm"
date: 2020-04-12 05:37 +09:00
---

*A*와 *B*를 [체](https://ko.wikipedia.org/wiki/체_(수학)) *F*에 대한 [정사각행렬](https://ko.wikipedia.org/wiki/행렬#정사각행렬)이라고 하자. 두 행렬의 곱 *C*는 다음과 같다.



만약 *A*와 *B*가 2n × 2n 꼴의 크기가 아니라면 먼저 모자라는 행과 열을 0으로 채운다. 이 경우 행렬 곱셈이 끝난 뒤 행렬에서 필요한 부분만 다시 잘라 내야 한다.

이제 *A*, *B*, *C*를 같은 크기의 정사각행렬 네 개로 나눈다.



이 때,



따라서 다음이 성립한다.

