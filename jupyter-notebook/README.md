# Jupyter Notebook

## Jupyter Notebook 이란?
데이터 분석을 하다보면, 내가 어떤 것을 분석할지 계획하고 어떻게 분석 했는지
정리/기록해야 하며 그 작업들이 파이썬과 같은 프로그래밍 언어를 통해 이루어질
필요성을 느끼게 되는데요.
즉 Jupyter Notebook 은 이 필요성을 충족시켜주는 데이터 분석용 파이썬 편집기라 할
수 있습니다.

## Jupyter Notebook 특징

- 살아있는 파이썬 문서를 만들어 문서화, 시각화, 분석을 용이하게 만들어주는 개발
환경입니다.
- 웹에서 코딩가능.
- 프로그램 코드를 브라우저에서 실행해주는 대화식 환경.
- 탐색적 데이터 분석에 적합.
- **아나콘다 설치시 자동으로 설치됨.**

## Jupyter Notebook 실행

시작 > Anaconda3 (64-bit) > Jupyter Notebook을 클릭합니다.
또는, 명령 프롬프트를 실행(윈도우 키+R을 누른 뒤 cmd를 입력)한 뒤 다음 명령을 입력합니다.

``` C:\Users\<사용자계정>\Anaconda3\python.exe -m notebook ```

cmd 창에  ```jupyter notebook``` 을 입력하면 실행 됩니다.

실행 : C:\Users\82108>jupyter notebook


## Jupyter Notebook 주요 단축키


### 셀 선택 모드 (Command Mode)


[esc] 또는 [ctrl] + [m]를 눌러 셀이 아래와 같이 파란색이 된 상태(셀 선택 모드)에서 해당 단축키 누른다.


위로 셀 추가 : [a]


아래로 셀 추가 : [b]


선택 셀 삭제 : [d][d] (d를 두번 누름)



선택 셀 잘라내기 (삭제로 써도 무방) : [x]


선택 셀 복사하기 : [c] 



선택 셀 아래에 붙여넣기 : [p] 



선택 셀과 아래 셀과 합치기 : [shift] + [m]


실행결과 열기/닫기 : [o]


Markdown으로 변경 :[m]


Code로 변경 : [y]


파일 저장 : [ctrl] + [s] 또는 [s] 


선택 셀의 코드 입력 모드로 돌아가기 : [enter]


### 코드 입력 모드 (Edit Mode)


[enter]를 눌러 셀이 아래와 같이 초록색이 된 상태(코드 입력 모드)에서 해당 단축키 누름


선택 셀의 코드 전체 선택 : [ctrl] + [a]


선택 셀 내 실행 취소 : [ctrl] + [z]


선택 셀 내 다시 실행 : [ctrl] + [y]


커서 위치 라인 주석처리 : [ctrl] + [/]


선택 셀 코드 실행 : [ctrl] + [enter]


선택 셀 코드 실행 후 다음 Cell로 이동 (없으면 새로 추가) : [shift] + [enter]


커서 위치에서 셀 둘로 나누기 : [shift] + [ctrl] + [-]


파일 저장 : [ctrl] + [s]


셀 선택 모드로 돌아가기 : [esc] 또는 [ctrl] + [m]
