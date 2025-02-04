# 입력 - scanf() 함수
---
scanf 함수
---
> scanf() 함수란<br>
```
- 표준 입력장치(키보드)로부터 값을 입력받을때 사용하는 함수
- 'f'는 fomat을 뜻함 -> 서식문자를 사용한다는 의미
- 주로 오류때문에 scanf()함수보다는 scanf_s()함수를 많이 씀.
```
> 사용의 예시<br>
```
#include <stdio.h>
- 정수 1개를 받을 시-
int main() {
  int num = 0;
  printf("정수를 입력해주세요.>>);
  scanf_s("%d", &num);                      -> &(공간 참조자, 참조 연산자) : 공간의 주소값을 반환
  return 0;
}
- 정수두개이상 받을시 -
int main() {
 int num1 = 0;
 int num2 = 0;
 "
 ..
 printf("정수를 N개 입력해주세요>>")
 scnaf_s("%d%d....", &num1, &num2, ...)      -> 주의점 : %d사이에 space가 들어가면 오류가 발생할 수 있기에 사이사이는 붙여준다.
 return 0;
}
```
---
서식문자와 scanf_s
---
> 개요<br>
- scanf()를 숫자 받기 + 문자 받기 이렇게 번갈아가며 입력을 받을 시에 입력사이에 rewind(stdin)을 넣어줘 버퍼공간을 초기화해주어야 함.
- 만일, 그렇지않으면 버퍼 공간에 남아있는 글자나 문자 값들이 다음 입력값에 영향을 미침.
> rewind(stdin)<br>
- Stream의 파일 위치 지시자(포인터)를 파일 시작위치로 옯기는 함수
- => 버퍼에 남아있는 값들을 지우는 작업이라 생각하면 쉽다.
---
실수 입력
---
> 사용<br>
- float형 입력 서식문자 : %f
- double형의 입력 서식문자 : %lf
```
#include <stdio.h>
int main() {
  float n1 = 0.0F;
  double n2 = 0.0;
  printf("실수 입력 : ");
  scanf_s("%f", &n1);          -> float형 입력 서식문자 %f
  printf("실수 입력 : ");
  scanf_s("%lf", &n2);         -> double형 입력 서식문자 %lf
```
---
한 문자 입력
---
> 사용<br>
- char형 입력 서식문자 : %c
- sizeof()(메모리 공간을 몇 byte차지하는지 확인해주는 함수)로 저장공간의 크기를 정수형으로 반환
```
#include <stdio.h>
int main() {
  char ch = NULL;      -> NULL : 반문자, 싱제로 NULL은 초기화로 적합하지 않음.
                       -> NULL을 초기화로 사용하는건 포인터 변수에 사용되는 값.
  => char ch; 로 바꾸는게 맞긴함.
  printf("영문으로 한 문자를 입력해주세요>");
  scanf_s("%c", &ch, sizeof(ch));            -> sizeof 저장공간의 크기를 정수형으로 반환
  return 0;
}
```
---
문자열 입력
---
> 사용<br>
- 배열은 &가 생략될 수 있다.
- 문자열은 한문자로 나눠서 배열에 한문자씩 각각 담는다고 생각하자
```
#include <stdio.h>
int main() {
  char name[20];        -> name이라는 배열의 크기는 21칸이며 NULL제외 총 20문자를 담을 수 있는 배열생성
  printf("이름 : ");
  scanf_s("%s, name, sizeof(name));
  return 0;
}
```





























