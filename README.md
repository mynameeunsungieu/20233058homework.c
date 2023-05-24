
# 리눅스명령어:top,ps,jobs,kill
![다운로드](https://github.com/mynameeunsungieu/20233058homework.c/assets/133843502/1c47ffe6-5b14-4329-bbe3-e9f05b53c557)

___


## **top: table of processes**

* top 명령어는 table of processes 의 약자로  CPU 와 메모리 이용에 관한 정보를 표시하는 수많은 유닉스 계열 운영 체제에서 볼 수 있는 작업 관리자 프로그램입니다.    
* 옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌

## **top 실행 전 옵션**

* 순간의 정보를 확인하려 `-b` 옵션 추가
* `-n` :top 실행 주기 설정(반복 횟수)

## **top 실행 후 옵션**

* `shift + p`: CPU 사용률 내림차순
* `shit + m` : 메모리 사용률 내림차순
* `shift + t`: 프로세스가 돌아가고 있는 시간 순
* `k` : kill. k 입력 후 PID 번호 작성. signal은 9
* `f` : sort field 선택 화면 -> q 누르면 RES순으로 정렬
* `a` : 메모리 사용량에 따라 정렬
* `b` : Batch 모드로 작동
* `1` : CPU Core별로 사용량 보여줌

## **ps: process status**

* ps 명령어는 process status 의 약자로 현재 실행중 프로세스 목록과 상태를 보여줍니다.
* ps 명령어 사용법
```
$ ps [option]

System V : $ ps -ef
BSD : $ ps aux
```

## **ps 주요 옵션**

* `-e`: every(모든)프로레스
* `-f`: ful(완전한)포멧
* `-l`: long(긴)포멧

## **사용 방법**

* `$ ps -ef`: 모든 프로세스를 풀 포맷으로 출력
* `$ ps -ef | grep '프로세스명'`: '프로세스명'의 프로세스 구동 확인
* `$ ps aux`: 실행 중인 모든 프로세스 확인
* `$ ps auxf`: 실행 중인 프로세스를 트리 구조로 보여줌
* `$ ps auxfww`: 실행 중인 프로세스를 트리구조 + 모든 실행 중인 옵션 확인 가능
* **※ ww 옵션을 제외하면 모든 라인이 다 안 보이지만, ww 옵션을 넣으면 다 보입니다.** 
* **ww을 안 했을 때**
![image01](https://github.com/mynameeunsungieu/20233058homework.c/assets/133843502/d2f90a35-8511-4a7d-9d8d-32c19c7abd07)

* **ww을 했을 때**

![image02](https://github.com/mynameeunsungieu/20233058homework.c/assets/133843502/c15b4a8b-7446-4f3f-a7f7-5506d2e7c77d)

## **jobs**

* jobs는 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경 되었지만 보고되지 않은 상태 등을 표시하는 명령어다.
* jobs 명령어 사용법
```
jobs[옵션][job ID]
jobs-x command [args]
```

## **jobs 주요 옵션**

* `-l`: 프로세스 그룹 ID를 state 필드 앞에 출력
* `-n`: 프로세스 그룹 중에 대표 프로세스 ID를 출력
* `-p`: 각 프로세스 ID에 대해 한 행씩 출력
* `command`: 지정한 명령어를 실행

## **※ jobs로 알 수 있는 세션의 상태 값**

* `Running`: 작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임
* `Done`: 작업이 완료되어 0을 반환하고 종료 했음을 의미
* `Done(code)`: 작업이 정상적으로 완료되었으며, 0을 반환하고 종료 했음을 의미
* `Stopped`: 작업이 일시 중단
* `Stopped(SIGTSTP)`: SIGTSTP신호가 작업을 일시 중단
* `Stopped(SIGSTOP)`: SIGSTOP신호가 작업을 일시 중단
* `Stopped(SIGTTIN)`: SIGTTIN신호가 작업을 일시 중단
* `Stopped(SIGTTOU)`: SIGTTOU신호가 작업을 일시 중단

## **kill**

* kill 명령어는 대개 프로세스를 죽일 때 사용합니다. 하지만 내부족으로는 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어입니다.
* kill 명령어 사용법
```
$ kill [옵션]<pid>[...]
```

## **프로세스 죽이는 방법**

* 죽이려는 프로세스의 pid를 얻은 다음 kill 명령어의 인자로 넘기면 됩니다.
* `$kill [pid]`
* 예를 들어 node.js로 실행 중인 서버를 죽이고 싶다면 ps 명령어를 통해 node.js의 pid를 얻고 kill 명령어의 파라미터로 넘겨 실행시키면 종료시킬 수 있습니다. 

## **사용자 지정 시그널 전송 방법**

* kill 명령어의 default 시그널은 TERM(15)입니다. 하지만 -s 명령으로 다른 시그널을 보낼 수 있습니다.
* `$kill -s [signal][pid]`
* 예를 들어 프로세스가 TERM(15) 시그널에 응답하지 않으면 다음의 명령어 처럼 KILL(9)를 사용해 강제로 죽일 수 있습니다.
* `$kill -s KILL [pid]`

## **사용 가능한 시그널의 목록**

* -l (List의 엘) 명령어를 통해 지원하는 시그널의 목록을 확인할 수 있습니다.

## **시그널을 보내는 다른 방법**

`$kill -s KILL [pid] $kill -s SIGKILL [pid] $kill -s 9 [pid] $kill -9 [pid]`
