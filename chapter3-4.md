# 열거형
- 열거형이란 프로그래머가 프로그래밍을 할 때 가독성을 위해 탄생한 데이터 형태
- 흔히 우리가 int라고 하여 값을 줄 수 있지만 이는 굉장히 기계친화적이며, 기계친화적이라 함은 사람에게는 굉장히 불편하다는 것이다.

```cpp
enum Day{
    SUNDAY = 0, MONDAY, TUESDAY, WEDNESSDAY, THURSDAY, SATURDAY
};

enum class Gender{
    MALE, FEMALE
};
// enum class 끼리는 내부에서 요소 이름이 중복되어도 문제없이 사용가능

int main(){
    Day d = Day::MONDAY;
    Gender gender = Gender::MALE; // enum class 이용시 무조건 형태를 지정해 주어야 함
    int value = (int*)gender; // 또한 int형에 넣을 떄는 캐스팅도 해줘야 함
}

```