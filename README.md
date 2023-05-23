
# 리눅스명령어:top,ps,jobs,kill
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
