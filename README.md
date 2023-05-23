
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
