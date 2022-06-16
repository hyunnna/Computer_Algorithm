---
layout: post
read_time: true
show_date: true
title:	Huffman Algorithm
date:   2022-04-01 08:12:32 -0600
description : 
tags: [algorithm]
author: HyunHwa
github: hyunnna
---

# <span style="color:Salmon">**Huffman Algorithm**  </span>  

### : **허프만 코딩(Huffman coding)** 은 텍스트 압축을 위해 널리 사용하는 방법이다.  
* 원본 데이터에서 자주 출현하는 문자는 적   은 비트의 코드로 변환하여 표현하고, 출현 빈도가 낮은 문자는 많은 비트의 코드로 변환하여 표현함으로써 전체 데이터를 표현하는데 필요한 비트 수를 줄이는 방식이다. 
* 이 압축 과정에서 허프만 트리를 구성하게 된다.

<br />

### <span style="color:Salmon">**시간복잡도** </span>



<br />

### <span style="color:Salmon">**LOGIC** </span>  
1. 문자열을 입력 받는다
2. 입력받은 문자열을 문자 단위로 끊어 해쉬 맵에 저장한 뒤에 빈도수를 체크한다.
3. 이후에 빈도수가 1 이상인 문자에 한해서 우선순위 큐에 삽입한다.
4. 우선순위 큐에 삽입하면서 자동으로 빈도수라는 우선순위에 따라 최소 힙과 같은 형태가 된다.
5. 루트 노드에서부터 순회하며 0 or 1을 붙여 허프만 코딩 알고리즘을 적용한다.
6. 결과적으로 처음 입력 받은 문자열을 해쉬 맵과 대조하여 압축된 2진형을 출력한다.  

<br />

### <span style="color:Salmon">**CODE** </span> 

```java
impotr.java.until *;


```

***
###### 참고 : https://blog.naver.com/ndb796/220829142548