---
layout: post
title: "[tech] Shell Script 함수 백그라운드 실행"
date: 2018-08-21 22:50:01 +0900 
tags: [tech, shellscript, 셸스크립트, background execute, 백그라운드 실행, 함수형, function]
categories: tech
comments: true
published: true
---
### Working
* 전체 서버의 특정 응답값을 체크해야하는 상황
* 이를 간단히 shell로 작업하여 각 서버의 응답값 체크
* 서버가 많다보니 응답값에 차이가 발생 
* shell 실행을 백그라운드로 실행 가능한데, function 또한 동일 하게 백그라운드로 가능함을 구글에서 확인

### Code
```shell
#! /bin/bash

function check() {
	for idx in `seq $1 $2`
	do
		# do something
		echo $idx
	done	
}

check 1 10 &
check 11 20 &
check 21 30 &
check 31 40 &

wait

# backgroup working end
echo "end background process"
```

### Wording
* bash shell 에서 function을 백그라운드로 실행하게되면 기동된 shell의 자식프로세스로 동작하게됨
* jobs 명령어를 통해서 관련 프로세스를 확인할 수 있으며, wait 를 사용할 수 있다.
* 백그라운드로 실행되는 function에서 사용되는 변수는 전역이 아닌 로컬변수로 이에 따라 부모의 전역변수에 데이터를 set하지 못함
* 아래 코드의 최종출력값은 1 이다.  

```shell
#! /bin/bash

gVal=1

function test() {
	gVal=$1
}

test 10 &

echo $gVal
```
* 이런 조건에 따라 백그라운드 작업의 결과를 확인하기 위해 간단히 파일을 이용함 (다른 방법이 무엇이 있을까?)


### 참고링크
* [작업 제어 명령어](https://wiki.kldp.org/HOWTO/html/Adv-Bash-Scr-HOWTO/x5472.html)