# Union
```C
#include <iostream>

using namespace std;

union tag {
    unsigned int a;
    unsigned short b[2];
    unsigned char c[4];
};

void main() {
    tag a;

    a.c[0] = 'a';
    a.c[1] = 'b';
    a.c[2] = 'c';
    a.c[3] = 'd';

    cout << a.a << endl;
    cout << a.b[0] << " " << a.b[1] << endl;
    cout << a.c[0] << " " << a.c[1] << " " << a.c[2] << " " << a.c[3] << endl;
}
```

> 멤버변수가 하나의 메모리 공간을 공유한다.