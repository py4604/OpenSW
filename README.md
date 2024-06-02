# OpenSW



## top 명령어

시스템의 상태를 전반적으로 가장 빠르게 파악 가능(CPU, Memory, Process)

옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌

1. top 실행 전 옵션
+ 순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)
+ -n : top 실행 주기 설정(반복 횟수)
2. top 실행 후 명령어
+ shift + p : CPU 사용률 내림차순
+ shit + m : 메모리 사용률 내림차순
+ shift + t : 프로세스가 돌아가고 있는 시간 순
+ k : kill. k 입력 후 PID 번호 작성. signal은 9
+ f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
+ a : 메모리 사용량에 따라 정렬
+ b : Batch 모드로 작동
+ 1 : CPU Core별로 사용량 보여줌
3. ps와 top의 차이점
+ ps는 ps한 시점에 proc에서 검색한 cpu 사용량
+ top은 proc에서 일정 주기로 합산해 cpu 사용율 출력

## ps 명령어

ps 명령어는 Process State의 약자로 현재 실행 중인 프로세스와 상태를 출력하는 명령어 

+ ps : 사용자와 관련된 프로세스만 출력
+ A : 모든 프로세스 출력
+ a : 터미널과 연관된 프로세스를 출력, x 옵션과 같이 사용하여 모든 프로세스를 출력할 때 사용
+ -a : 세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력
+ -e : 커널 프로세스를 제외한 모든 프로세스를 출력
+ -f : 출력을 풀 포맷으로 표기, (유닉스 스타일) UID, PID , PPID 등이 함께 표시
+ -l :  출력을 긴 포맷으로 표기, 프로세스의 정보를 길게 보여주는 옵션으로 우선순위와 관련된 PRI 값과 NI 값을 확인
+ -o : 출력 포맷을 지정
+ -M : 64비트 프로세스들을 출력
+ -m : 프로세스뿐만 아니라 커널 스레드도 출력
+ -p : 특정 PID를 지정하여 출력
+ -r : 현재 실행 중인 프로세스 출력
+ u (BSD) : 프로세스의 소유자를 기준으로 출력
+ -u [사용자] : 특정 사용자의 프로세스 정보를 출력, 사용자를 지정하지 않는다면 현재 사용자 기준으로 출력
+ x (BSD) : 데몬 프로세스처럼 터미널에 종속되지 않은 프로세스를 출력
+ -x : 로그인 상태에 있는 동안 아직 완료되지 않은 프로세스를 출력

## jobs 명령어

jobs 명령어로 셸에서 실행중인 프로세스 목록을 확인가능함

+ jobs : 명령어는 옵션이나 인자 없이 주로 사용, 단, 실행중인 작업이 없다면 아무것도 출력되지 않음.
+ -l : 프로세스 ID와 함께 잡 목록을 출력
+ -n : 마지막로 알림 이후 변경된 잡만 출력
+ -p : 잡의 프로세스 ID만 출력
+ -r : 실행 중인 잡만 출력
+ -s : 중지된 잡만 출력

## kill 명령어

kill 명령어는 프로세스에 시그널(signal)을 보내어 원하는 동작을 수행할 수 있음
 
프로세스 종료 외에도 다른 신호를 보내어 프로세스의 동작을 제어할 수도 있음

+ kill [option] <PID> : 해당 PID의 프로세스 종료
+ -s <signal> : 특정 시그널(signal)을 사용하여 프로세스를 종료합니다. 기본적으로 SIGTERM 시그널이 사용됩니다.
+ -l, --list : 지원되는 시그널(signal) 목록을 출력합니다.
+ -a, --all : 현재 사용자에 속한 모든 프로세스를 종료합니다.
+ -q, --queue : 프로세스에 시그널을 보내는 대신 시그널을 대기열에 추가합니다.
