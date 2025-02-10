# 배열
---
배열
---
> 배열이란<br>
- 연관된 데이터를 각각의 인덱스 변호를 할당하여 나열한 자료 구조 형태
```
인덱스      0      1      2      3      4      5      6
자료       12     123    231    222    54      1      59
-> 이때 배열의 인덱스 번호로 배열 안의 자료(데이터)에 접근할 수 있다.
```
> 배열의 필요성<br>
- 번호를 매개야하는등 같은 작업을 여러번 반복하는 경우 배열을 통해 간단히 정리가 가능
- 즉, 배열은 인덱스를 사용하여 각 요소에 대한 접근이 용이함
> 배열의 선언<br>
```
int          arr            [?]
자료형     배열의 이름     배열의 크기
```
> 전처리문-define<br>
- C/C++에서 사용하는 전처리기 지시문임. 상수 또는 매크로 정의할 수 있음
```
(EX)
#include <stdio.h>
#define STUDENTS 6          --> STUDENTS의 값은 항상 6임을 명시
int main(void) {
    int grade[STUDENTS]     --> 배열의 크기가 STUDENTS인 즉 6칸인 배열임
    int sum = 0;
    int average = 0;
    for (int i = 0; i < STUDENTS; i++) {
        printf("학생들의 성적을 입력해주세요>>\n");
        scanf_s("%d, &grade[i]);
        sum += grade[i];
    }
    average = sum / STUDENTS;
    printf("성적 평균 = %d\n", average);
    return 0;
}
====> 즉 학생의 총수가 아무리 변경되더라도 전처리문인 students의 값만 변경하면 하나하나 변경할 필요없이 자동적용이기에 편리함
```


























