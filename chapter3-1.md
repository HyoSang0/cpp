# 객체 지향의 기본
* Object Oriented Programming  
* 속성과 행동을 나누는 것을 추상화라고 한다  

# 클래스 멤버 / 생성자 / 소멸자
## 클래스
* class 키워드를 이용해 클래스를 생성할 수 있다.  
* 클래스의 내부에는 꼭 public: 이라는 키워드가 있어야 한다.  
* 클래스 안에는 함수도 선언할 수 있다.

### c++식 동적할당
```c++
Student* ps = new Student(); // new로 만들고
ps->student_num = 3456
strcpy(ps->name, "김순이");
ps->gender = 1;
delete ps // delete로 삭제
```

## 생성자
* 클래스는 생성자를 통해 초기 행동을 지정해줄 수 있다.
* 생성자는 클래스명(파라미터들...)로 선언할 수 ㅣㅇㅆ다.
* 생성자는 리턴타입을 가지지 않는다.

### this 키워드
* 클래스 내부의 변수와 함수 매게변수의 이름이 같다면 this를 사용할 수 있다.
* 클래스 멤버 함수는 this라는 키워드를 통해 자기자신의 인스턴스(포인터 타입)를 가져올 수 있다.
* 클래스 멤버 함수를 호출하기 위해서는 호출한 주체인 어떤 클래스 인스턴스가 존재하게 되는데 그 호출 주체를 this라고 한다.

## 소멸자
* 클래스는 소멸자를 통해 메모리에서 해제될 때의 행동을 지정해줄 수 있다.
* 소멸자는 ~클래스명()으로 선언할 수 있다.
* 소멸자도 리턴타입과 매게변수를 가지지 않는다.
* 정적할당한 클래스는 자동적으로 소멸자를 호출한다.
* 동적할당한 클래스틑 delete를 사용해야한다.

```c++
class Student{
    public:
    int student_num;
    char name[20];
    int gender; // 0 = 남자, 1 = 여자
    
    Student(int pStdNo, const char* n, int g){
        student_num = pStdNo;
        strcpy(name, n);
        gender = g;
    }
    ~Student(){
        printf("%s의 소멸자 호출\n", this->name);
    }
    
    void printStudentInfo(){
        printf("%d", student_num);
        printf("%s", name);
        printf("%s", gender == 0 ? "남자" : "여자");
    }
}
int main(){
    Student s = Student(123, "김말똥", 0);
    /*
    s.student_num = 123;
    strcpy(s.name, "김말똥");
    s.gender = 0;
    */
    s.printStudentInfo();

    Student* ps = new Student();
    ps->student_num = 456
    strcpy(ps->name, "김순이");
    ps->gender = 1;

    ps->printStudentInfo();

    delete ps;

    return 0;
}
```