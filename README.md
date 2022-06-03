# README_2022


---

top, ps, jobs, kill
매크로 사용방법 (q)
***
**TOP**

시스템의 프로세스/메모리 사용 상태를 5초의 간격으로 업데이트하여 출력한다.

화면에 출력되는 기본값은 현재시간, 시스템 업데이트(1) 시간, 시스템에 로그인한 사용자 수, 지난 1분, 지난 5분, 지난 15분간의 시스템 평균 부하를 출력한다.

***
**top 실행 후 명령어**

shift + p : CPU 사용률 내림차순

shit + m : 메모리 사용률 내림차순

shift + t : 프로세스가 돌아가고 있는 시간 순

k : kill. k 입력 후 PID 번호 작성. signal은 9

f : sort field 선택 화면 -> q 누르면 RES순으로 정렬

a : 메모리 사용량에 따라 정렬

b : Batch 모드로 작동

1 : CPU Core별로 사용량 보여줌

***
![TOP](https://user-images.githubusercontent.com/106612302/171804770-64b5fd54-65b9-490b-887a-cef935c42b15.png)

***


**1) 시간정보** = 현재시간, 컴퓨터 실행시간 (uptime 명령어)

**2) load average:** 시스템 부하정도를 나타내는
                 1분, 5분, 15분 시스템 부하평균값(EMA)

     -  'R'  실행중인 프로세스
     -  'D' 디스크  I/O 처리완료를 기다리는 프로세스



**3) Task(프로세스) 정보**
 


**4) CPU 사용율 % **
 
 - us : user - mode (높은 우선순위 nice 0또는 음수)
 
 - sy : kernel - mode
 
 - ni : user - mode (낮은 우선운위 nice 양수)
 
 - id : idle (시스템이 얼마나 여유러운지)
 
 - wa : I/O wait (처리완료를 기다린 시간)
 
 - hi : hard irq (인터럽트 전반부처리(빠른처리))
 
 - si : soft irq (인터럽트 후반부처리(지연처리))
 
 - st : 가상 CPU 구동 (Guest OS를 위한 VM 처리)



**5) MEM 사용율 %**

 * total : 총 메모리 공간 KB

 * free : 남은 메모리 공간 KB

 * used : 사용중인 메모리 공간 KB

 * buff/cache : 디스크에 있는 내용을 메모리에 캐시 KB

 * available :프로세스가 처음시작시 사용가능한 메모리 공간 KB
             (회수하면 얻을 수 있는 공간 포함)

 * swap : 메모리의 내용을 저장해둘 수 있는 Disk 공간 KB




**6) 프로세스 세부정보**

 * PID: 프로세스 ID

 * PR: 20 + nice

 * NI: nice (친절도)

 * VIRT: 가상메모리공간

 * RES: 실제 사용중인 물리메모리 공간

 * SHR: 공유메모리 공간

 * S: 프로세스 상태 (STATE)
    
   -  'D' = uninterruptible sleep (예시: 디스크I/O처리대기)
    
   -   'R' = running
    
   -   'S' = sleeping (예시: 네트워크 I/O 처리대기)
    
   -   'I' = idle (예시: sleep 중인 kernel thread)
    
   -   'T' = stopped by job control signal
    
   -   't' = stopped by debugger during trace
    
   -   'Z' = zombie
   
 * %CPU: CPU 사용율

 * %MEM: 메모리 사용율

 * TIME+: 프로그램 실행한시간


참고 정보: man top, proc 및 커널 소스, top 소스코드

***

***ps***

현재 동작하고 있는 프로세스에 대한 정보(목록 및 상태)를 보여줌

***
**전체 프로세스와 관련된 옵션**

 - -A : 모든 프로세스를 출력한다.

 - -N : -A 옵션과 비슷하나 ps 프로세스를 제외하고 출력한다.

 - -a : 세션 리더 및 터미널에 속하지 않는 프로세스를 제외하고 출력한다.

 - -d : 세션 리더를 제외한 모든 프로세스를 출력한다.

 - -e : 커널 프로세스를 제외한 모든 프로세스를 출력한다.

 - T : 현재 터미널에서의 모든 프로세스를 출력한다.

 - a : 현재 터미널의 사용자 고유 프로세스를 출력한다.

 - r : 현재 실행 중인 프로세스를 출력한다.

 - x : 터미널이 없는 프로세스를 출력한다.

 - --deselect : -N 옵션과 같다.


**특정 프로세스를 선택하여 보여주는 옵션**

 - -C : 지정한 명령어의 이름에 관련된 정보를 출력한다.

 - -G : 그룹 ID에 관련된 정보를 출력한다(이름도 지원).

 - -U : 사용자 ID에 관련된 정보를 출력한다(이름도 지원).

 - -g : 지정한 세션 리더 혹은 그룹명에 관련한 정보를 출력한다.

 - -p : 프로세스 ID를 출력한다.

 - -s : 세션에 속한 프로세스를 지정한다.

 - -t : tty를 지정한다.

 - -u : 사용자 ID를 지정한다(이름도 지원).

 - U : 지정한 사용자의 프로세스를 출력한다.

 - p : 프로세스 ID를 지정한다.

 - t : tty를 지정한다.



 - --Group : 실제 그룹 이름이나 ID를 지정한다.

 - --User : 실제 사용자 이름이나 ID를 지정한다.

 - --group : 유효 사용자 이름이나 ID를 지정한다.

 - --pid : 프로세스 ID를 지정한다.

 - --sid : 세션 ID를 지정한다.

 - --tty : 터미널을 지정한다.

 - --user : 유효 사용자 이름이나 ID를 지정한다.

 - -123 : --sid 123과 같은 의미이다.

 - 123 : --pid 123과 같은 의미이다.


**프로그램의 정보**

 - -V : 버전 정보를 출력한다.

 - L : 모든 형태의 지시자를 출력한다.

 - V : 버전 정보를 출력한다.

 - --help : 사용법을 출력한다.

 - --info : 디버깅 정보를 출력한다.

 - --version : 버전 정보를 출력한다.
 
***

**ps명령어**

>ps ax

시스템에 동작중인 모든 프로세스를 보고 싶을 때 위와 같은 명령어를 사용하면 BSD 포맷으로 출력함

>ps aux 

시스템에 동작중인 모든 프로세스를 소유자 정보와 함께 다양한 정보를 출력함

>ps -ef | more

'ps -ef'는 System V 계열 옵션으로 'ps aux'처럼 시스템에 동작중인 모든 프로세스를 full format으로 출력함

>ps -el | head

긴 포맷으로 출력하고 싶을 경우 -l 옵션을 사용해줍시다. 보면 'ps -ef'에서 보이지 않았던, F, S, PRI, NI, ADDR~ 등등 더 많은 정보들이 출력되는 것을 확인 가능함

>ps -fp [PID]

PID를 키워드로 프로세스 정보를 확인하는 방법

>s -U root -u root

특정 사용자가 돌리는 프로세스의 정보를 알고 싶을 때 real uid와 uid를 의미하는 옵션으로 셀렉할 수 있음 (root가 돌리는 프로세스를 확인하는 명령어)

>ps -t pts/18

특정 TTY에서 실행되는 프로세스 또한 뽑아서 확인할 수 있음

>ps -e -o pid,ppid,uname,pcpu,pmem,comm,tty | head

-o 옵션을 사용하면 원하는 컬럼만 보이도록 포맷을 정할 수 있음

>ps -p 1222 -o comm=

PID가 1222인 프로세스의 이름을 출력함

>ps -C httpd -o pid=

이름이 httpd인 프로세스들의 pid를 출력함

***
***jobs***

작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태 등을 표시한다.

***
![jobs-1](https://user-images.githubusercontent.com/106612302/171805560-396a33cf-62a1-4900-8013-0b4644b011c5.jpg)

-l 옵션은 state 필드 앞에 프로세스 ID를 출력한다.

![jobs-2](https://user-images.githubusercontent.com/106612302/171805610-9f2238dc-d5fe-4ae1-844b-2c6487fc0ddb.jpg)


 - -l : 프로세스 그룹 ID를 state 필드 앞에 출력한다.
 - -n : 프로세스 그룹 중에 대표 프로세스 ID를 출력한다.
 - -p : 각 프로세스 ID에 대해 한 행씩 출력한다.
 -  command : 지정한 명령어를 실행한다.

  **jobs -p %v를 하면 v로 시작하는 모든 프로세스 ID를 확인할 수 있다.**

 - Running : 작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임을 뜻한다.

 - Done : 작업이 완료되어 0을 반환하고 종료했음을 뜻한다.

 - Done (code) : 작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환했음을 뜻한다.

 - Stopped : 작업이 일시 중단됨을 뜻한다.

 - Stopped (SIGTSTP) : SIGTSTP 신호가 작업을 일시 중단했음을 뜻한다.

***

***kill***

***
![kill-removebg-preview](https://user-images.githubusercontent.com/106612302/171830574-fef496b1-c43d-4124-b05b-c31c05b66490.png)
|사진|설명||
|---|---|---|
|Root|USER|프로세스의 사용자|
|2518|PID|프로세스 ID|
|0.0|%CPU|마지막 1분 동안 프로세스가 사용한 CPU 점유율|
|0.1|%MEM|마지막 1분 동안 프로세스가 사용한 메모리의 점유율|
|7084|VSZ|가상메모리에 있는 프로세스의 KB 단위 크기|
|1076|RSS|프로세스의 실제 메모리의 크기로 KB 단위|
|?|TTY|연결되어 있는 터미널|
|Ss|STAT|실행되고 있는 프로세스 상태|
|Jun07|START|프로세스가 시작된 날짜|
|0:00|TIME|프로세스가 소비한 총 시간|
|/usr/sbin/sshd|COMMAND|사용자가 실행한 명령 이름|

**ps 명령으로 확인한 PID를 이용하면 원하는 프로세스를 종료시킬 수 있다.**

kill [num] : [num]프로세스를 종료시킨다

kill -9 [num] : [num]프로세스를 강제로 종료시킨다


***kill -9 1 : 시스템이 다운된다.***

***
***매크로***

***
[매크로]<https://www.youtube.com/watch?v=wRFEBw02aT8>
