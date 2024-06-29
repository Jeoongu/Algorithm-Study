# sstream
- `std::iostream`을 상속받아서 멤버 함수와 그 부모 클래스들의 멤버 함수 모두 사용 가능하다.
- 문자열을 읽거나 쓸 때 편리한 방법을 제공하고 문자열로부터 값을 추출하거나 문자열에 값을 삽입할 때 사용한다.
- 코딩 테스트에서 문자열을 풀이할 때, C++ string만으로 해결하기 어려울 때 주로 사용된다.
- 코딩 테스트에서 날짜와 관련해서 많이 사용된다.

### include
- `#include <sstream>` C++ 코드에 include 가능하다.

### 종류
1. istringstream : 입력 스트림
2. ostringstream : 출력 스트림
3. stringstream : 입출력 스트림

### 사용 용도
1. **문자열 자르기**
- 문자열을 공백과 '\n'을 기준으로 여러 개의 다른 형식으로 차례때로 분리할 때 편리하다.
```cpp
#include <iostream>
#include <sstream>
#include <string>
using namespace std;

int main() {
	istringstream ss("test\n123 aaa 456"); // stringstream으로 사용해도 무관하다.
	string s1, s2;
	int i1, i2;
	ss >> s1 >> i1 >> s2 >> i2; // 문자열을 파싱하고 변수형에 맞게 변환한다. 중요

	cout << s1 << endl; // test
	cout << i1 << endl; // 123
	cout << s2 << endl; // aaa
	cout << i2 << endl; // 456
}
```

2. `str()`, `clear()`
- `str(string s)` : stringstream에 저장된 문자열을 바꾼다.
- `str()` : stringstream이 저장하고 있는 문자열의 복사본을 반환한다.
- `clear()` : stringstream을 재사용하려면 이 함수를 실행해야 한다. 이때 저장된 문자열이 삭제되진 않는다.

3. `get()`, `unget()`
- `get()` : 커서를 뒤로 옮기면서 값을 반환한다.
- `unget()` : 커서를 다시 앞으로 옮긴다.
```cpp
string str = "123abc";

// get()
stringstream ss1;
ss1.str(str);
cout << ss1.get() - '0'; // 1: -'0' 안해주면 아스키코드값이 나옴
cout << ss1.get() - '0'; // 2

// unget()
stringstream ss2;
ss2.str(str);
char ch;
ss2 >> ch; // 1
ss2 >> ch; // 2
ss2.unget();
ss2 >> ch; // 1
```

4. `getline()`
- 문자열을 공백이나 '\n'이 아닌 다른 문자를 기준으로 분리하고 싶을 때 사용한다. 
```cpp
#include <iostream>
#include <sstream>
#include <string>
using namespace std;

int main() {
	string str = "gkg|qiew|789", token;
	stringstream ss(str);
	while (getline(ss, token, '|')) {
		cout << token << endl;
	}
}

// 실행 결과
// gkg
// qiew
// 789
```
