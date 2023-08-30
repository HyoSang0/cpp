# 클래스 상속
* 클래스 선언 후 상속 받을 클래스의 이름 옆에 콜론 public 상속할 클래스 이름 순으로.

## 생성자 관련
* 새로운 클래스 인스턴스를 선언할 때 new className 으로 하는데 클래스 이름 뒤에 괄호는 있어도 되고 없어도 된다.
* 하지만 생성자가 정의되어 있다면 무조건 괄호를 입력하여야 한다.
* 부모 클래스에 생성자가 매개변수를 필요로 할 경우 자식 클래스의 생성자는 콜론과 부모 생성자를 한 번 더 써주고 인수를 넘겨주면 된다.

```cpp
class Animal {
public:
	int legs;
};

class Person : public Animal{
public:
	char regist_no[30];
};

int main() {

	Person p;
	p.legs = 2;

	return 0;
}
```

# 접근지정자
## public
* 누구나 접근 가능

# protected
* 본 클래스와 상속된 클래스 내부에서 접근은 가능하나 외부에서 접근은 안됨

## private
* 본 클래스 내부에서만 사용 가능함


