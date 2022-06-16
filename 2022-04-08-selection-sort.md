---
layout: post
read_time: true
show_date: true
title: Seleciton Sort
date:   2022-04-08 08:12:32 -0600
description : 
tags: [algorithm]
author: HyunHwa
github: hyunnna
---

# <span style="color:PeachPuff">**Selection Sort**  </span>  
<br />

***

## <span style="color:PeachPuff">**LOGIC**  </span> 

1. 배열의 각 셀을 왼쪽부터 오른쪽 방향으로 확인하면서 어떤 값이 최솟값인지 결정한다. 한 셀씩 이동하면서 현재까지 가장 작은 값을 기록한다. (실제로는 그 인덱스를 변수에 저장)  
변수에 들어있는 값보다 작은 값이 들어있는 셀을 만나면 변수가 새 인덱스를 가리키도록 값을 대체한다.  

2. 이제 최솟값이 어느 인덱스에 들어 있는지 알았으므로 그 인덱스의 값과 패스 스루를 처음 시작 했을때의 값을 교환한다.  
패스스루를 시작했을 때 인덱스는 첫 패스스루에서는 인덱스 0일 것이고, 두번째 패스스루에서는 인덱스 1일 것이다. 

3. 매 패스스루는 1,2단계로 이루어진다. 배열 끝에서 시작하는 패스스루에 도달할 때까지 패스스루를 반복한다. 


## <span style="color:PeachPuff">**CODE**  </span> 
```java
funtion selectionSort(array){
    for(let i = 0; i<array.length-1; i++){
        let lowestNumberIndex = i;
        for(let j =i +1; j<array.length; j++){
            if(array[j]<array[lowestNumberIndex]){
                lowestNumberIndex = j;
            }
        }
        if(lowestNumberIndex != i ){
            let temp = array[i];
            array[i] = array[lowestNumberIndex];
            array[lowestNumberIndex] = temp;
        }
    }
    return array;
}
```
<span style="color:#000; background-color:PeachPuff">**for (let i = 0;  i < array.length - 1; i++ )**  </span>  


    각 패스스루를 나타내는 루프 시작. 루프는 변수 i 를 이용해 각 값을 가리키며 끝에서 두번째 값까지 살펴본다.  

<span style="color:#000; background-color:PeachPuff">**let  lowestNumberIndex = i ;**  </span>  

    마지막 값을 시작하기 전에 이미 배열이 완전히 정렬되므로 마지막값은 보지 않아도 된다. 이어서 현재까지의 최솟값이 들어있는 인덱스를 저장한다.

<span style="color:#000; background-color:PeachPuff">**for(let j = i +1; j < array.length; j++**)  </span> 

    lowestNumberIndex는 첫 패스스루를 시작할 때는 0, 두번째 패스스루를 시작할 때는 1일 것이다. 
    특별히 인덱스를 저장하는 이유는 나머지 코드에서 최솟값과 그 인덱스를 모두 사용해야 하기 때문이고 인덱스를 사용하면 둘 다 참조할 수 있다.(array[lowestNumberIndex]를 호출해 최솟값을 확인할 수 있다.)  
    각 패스스루에서는 배열의 나머지 값들을 확인해 현재 최솟값보다 더 작은 값이 있는지 알아본다.

<span style="color:#000; background-color:PeachPuff">**if(array[j] < array[lowestNumberIndex]) {  
        lowestNumberIndex = j; }**  </span>  

    실제로 더 작은 값을 찾으면 이 값의 인덱스를 lowestNumberIndex에 저장한다.  


<span style="color:#000; background-color:PeachPuff">**if (lowestNumberIndex != i ){  
            let temp = array[i];  
            array[i] = array[lowestNumberIndex];  
            array[lowestNumberIndex] = temp;  
        }**  </span>

    안쪽 루프가 종료되는 시점에 이번 패스스루에서 가장 적은 수의 인덱스가 결정된다.  
    패스스루의 최솟값이 이미 올바른 위치에 있으면(최솟값이 패스 스루에서 만난 첫번째 값인 경우) 아무것도 하지 않아도 된다. 하지만 최솟값이 올바른 위치에 있지 않으면 교환해야 한다. 좀 더 구체적으로 설명하면 패스스루를 시작했던 인덱스 i에 있는 값과 최솟값을 교환한다.

    끝으로 정렬된 코드를 반환한다.