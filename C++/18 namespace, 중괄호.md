# {} 중괄호

```C
int main() {

    char a[] = "main : A";
    char b[] = "main : B";

    char *d;
    char *e;

    wcout << a << endl;
    wcout << b << endl << endl;

    {
        // {1}
        static char b[] = "{1} : static B";
        char c[] = "{1} : C";

        d = b;
        e = c;

        wcout << a << endl;
        wcout << b << endl;
        wcout << c << endl << endl;
    }
    {
        // {2}
        static char b[] = "{2} : static B";
        char c[] = "{2} : C";

        wcout << a << endl;
        wcout << b << endl;
        wcout << c << endl << endl;
    }

    wcout << a << endl;
    wcout << b << endl;
    //wcout << c << endl; //c에 접근할수 없다.
    wcout << d << endl;
    wcout << e << endl;  //원래대로면 접근하면 안된다.
}
```
> {} 호는 식의 지역을 생성한다.

> {} 괄호안의 지역 변수는 '}' 와 함께 사라진다.

> { { } } 괄호는 중첩될수 있다.

> 지역변수를 static으로 선언하면 전역변수로 취급한다.

# namespace

```C
#include <iostream>

using namespace std;

namespace _A {
static char b[] = "_A : static B";
char c[] = "_A : C";

class MyClass {
  public:
    static void out() {
        wcout << "_A" << endl;
        wcout << b << endl;
        wcout << c << endl << endl;
    }
};
}

namespace _B {
static char b[] = "_B : static B";
char c[] = "_B : C";

class MyClass {
  public:
    static void out() {
        wcout << "_A" << endl;
        wcout << b << endl;
        wcout << c << endl << endl;
    }
};

namespace _C {
static char b[] = "_C : static B";
char c[] = "_C : C";

class MyClass {
  public:
    static void out() {
        wcout << "_C" << endl;
        wcout << b << endl;
        wcout << c << endl << endl;
    }
};
}
}

int main() {
    _A::MyClass::out();
    _B::MyClass::out();
    _B::_C::MyClass::out();
}
```
> 전역공간에 이름을 가진 지역공간을 생성한다.

> static 클래스와 많은면에서 비슷한 구조를 가진다.