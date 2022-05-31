# README_2022


---

top, ps, jobs, kill
매크로 사용방법 (q)

**1) 시간정보** = 현재시간, 컴퓨터 실행시간 (uptime 명령어)
***
**2) load average:** 시스템 부하정도를 나타내는
                 1분, 5분, 15분 시스템 부하평균값(EMA)

     -  'R'  실행중인 프로세스
     -  'D' 디스크  I/O 처리완료를 기다리는 프로세스

***

**3) Task(프로세스) 정보**
 
***

**4) CPU 사용율 %**
 
 - us : user - mode (높은 우선순위 nice 0또는 음수)
 
 - sy : kernel - mode
 
 - ni : user - mode (낮은 우선운위 nice 양수)
 
 - id : idle (시스템이 얼마나 여유러운지)
 
 - wa : I/O wait (처리완료를 기다린 시간)
 
 - hi : hard irq (인터럽트 전반부처리(빠른처리))
 
 - si : soft irq (인터럽트 후반부처리(지연처리))
 
 - st : 가상 CPU 구동 (Guest OS를 위한 VM 처리)

***

**5) MEM 사용율 %**

 * total : 총 메모리 공간 KB

 * free : 남은 메모리 공간 KB

 * used : 사용중인 메모리 공간 KB

 * buff/cache : 디스크에 있는 내용을 메모리에 캐시 KB

 * available :프로세스가 처음시작시 사용가능한 메모리 공간 KB
             (회수하면 얻을 수 있는 공간 포함)

 * swap : 메모리의 내용을 저장해둘 수 있는 Disk 공간 KB


***

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
***
참고 정보: man top, proc 및 커널 소스, top 소스코드
