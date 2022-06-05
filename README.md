# open

---
## top
top 명령어는 **CPU와 Memory 등의 상태를**를 보여주는 명령어.

## [top 사용법]
$ top

## [top 옵션]

|옵션|설명|
|:---:|:---|
|-a|메모리 사용에 따라 정렬|
|-b|배치 모드에서 시작|
|-c|명령어 대신 명령어 라인을 보여줌|
|-h|도움말|
|-H|모든 개별 쓰레드가 보여짐|
|-i|좀비 또는 IDle상태의 것들은 무시됨|
|-n|반복의 최대 수를 지정|

## [top 실행중 명령어]

|명령어|설명|
|:---:|:---|
|스페이스바|화면 갱신|
|shift + p|CPU 사용률이 높은 프로세스 순서대로 표시|
|shift + m|메모리 사용률이 높은 프로세스 순서대로 표시|
|shift + t|프로세스가 돌아가고 있는 시간 순서대로 표시|
|k|kill 명령|
|r|nice 값을 변경. nice는 우선순위를 뜻하고 -20 ~ 20까지 사용가능. 낮을수록 우선권이 높음.|
|Z|화면 출력 색상 변경. a 또는 w|
|l|top 출력 상단의 Load avg 항목 on/off|
|t|top 출력 상단의 프로세스와 cpu항목 on/off|
|m|top 출력 상단의 메모리 항목 on/off|
|q|top 종료|


---
## ps
ps *(Process Status)* 명령어는 **현재 실행중인 프로세스 목록과 상태**를 보여주는 명령어다.
<img width="240" alt="ps" src="https://user-images.githubusercontent.com/103654549/172052287-3da2e02a-078f-441e-8d83-a35efa974ff4.png">

## [ps 사용법]
$ ps [option]

## [ps 옵션]

|옵션|설명|
|:---:|:---|
|-e|커널 프로세스를 제외한 모든 프로세스를 출력|
|-f|풀 포맷으로 보여줌 (UID, PID, PPID등이 함께 표시)|
|-l|긴 포맷으로 보여줌|
|p,-p|특정 PID의 프로세스를 보여줌|
|-u|특정 사용자의 프로세스 정보를 확인할 때 사용. 사용자를 지정하지 않으면 현재 사용자를 기준으로 정보를 출력|
|-ef|모든 프로세스를 풀 포맷으로 출력|
|aux|시스템의 동작중인 모든 프로세스를 소유자 정보와 함께 다양한 정보를 출력|
|auxf|시스템의 동작중인 프로세스를 트리구조로 출력|

---
## jobs
jobs 명령어는 **작업의 상태**를 표시하는 명령어다.

## [jobs 사용법]
$ jobs [옵션][작업번호]

## [jobs 옵션]

|옵션|설명|
|:---:|:---|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|
|command|지정한 명령어를 실행|

## [백그라운드 작업의 상태값]

|명령어|설명|
|:---:|:---|
|Running|작업이 일시 중단되지 않았고 종료하지 않고 계속 진행 중임.|
|Done|작업이 완료되어 0을 반환하고 종료했음.|
|Done (code)|작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환했음.|
|Stopped|작업이 일시 중단됨을 뜻함.|
|Stopped (SIGTSTP)|SIGTSTP 신호가 작업을 일시 중단했음.|
|Stopped (SIGSTOP)|SIGSTOP 신호가 일시 중단했음.|
|Stopped (SIGTTIN)|SIGTTIN 신호가 작업을 일시 중단했음.|
|Stopped (SIGTTOU)|SIGTTOU 신호가 작업을 일시 중단했음.|

---
## kill
kill 명령어는 **프로세스에 signal**을 보내는 명령어다. 일반적으로 종료되지 않는 프로세스를 종료 시킬 때 사용된다.

## [kill 사용법]
$ kill [옵션] [PID]

## [kill 옵션]

|옵션|설명|
|:---:|:---|
|-l|signal의 종류를 출력|

|번호|주요 시그널|설명|
|:---:|:---:|:---|
|1|SIGUP|세션이 종료될 때 시스템이 내리는 시그널|
|2|SIGINT|Ctrl + C, 종료 요청 시그널|
|9|SIGKILL|강제 종료 시그널|
|11|SIGSEGV|메모리 침범이 일어날 때 시스템이 보내는 시그널|
|15|SIGTERM|기본 값, 종료 요청 시그널|
|20|SIGTSTP|Ctrl + Z, 일시 중지 요청 시그널|

---
## [vim 에디터에서 Macro 사용]
*Macro* 는 **Vim 명령어들을 기록하고 반복**할 수 있는 기능이다.

#### [사용법]
1. 매크로 기록 시작은 **q{레지스터}**
+ *매크로가 저장될 register 주소로 a ~ z 사용 가능*
2. 'A'라는 매크로명으로 매크로 기록하고 사용한다고 가정. 
+ **qA -> 작업**
3. 매크로 기록 종료는 **q**

#### [실행 방법]
* '**@{레지스터}**' 로 저장된 매크로 실행 가능
* '**@@**' 로 직전에 실행한 매크로 재실행
* '**@@**' 로 직전에 실행한 매크로 재실행
* **'{반복횟수}@{레지스터}'** 또는 '**{반복횟수}@@**' 로 저장된 매크로를 **'반복횟수'**만큼 재실행 가능
