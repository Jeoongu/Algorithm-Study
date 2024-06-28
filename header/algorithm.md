# algorithm
- 코딩테스트 내에서는, 주로 vector container와 함께 사용되는 경우가 많다.

### include
- `#include <algorithm>` C++ 코드에 include 가능하다.

### 속한 함수들
- 속한 함수들이 많지만 자주 사용되는 것만 정리한다.

1. 대수 비교(min, max)
```cpp
#include <stdio.h>
#include <algorithm>

using namespace std;

int main(){
    int a = 10;
    int b = 5;

    printf("max: %d\n", max(a,b));
}
```
2. 정렬(sort)
- 기본적으로 작은 것부터 큰 것으로 정렬하는 오름차순 정렬을 수행한다.
- 내림차순 정렬을 수행하기 위해서는 `<functional>`의 `greater<int>()`를 사용해야 한다.
- vector를 정렬하고 싶을 때는 인자로 `begin()`, `end()`를 값으로 넣는다.
- 리턴값은 none이다.
```cpp
#include <stdio.h>
#include <algorithm>
#include <vector>
#include <funtional>

using namespace std;

int main(){
    vector<int> v1{7, 5, 4, 1, 3, 2, 6};
    sort(v1.begin(), v1.end(), greater<int>());
}
```

3. 순열(next_permutation, prev_permutation)
- next_permutation은 현재 vector(또는 array)로 표현된 순열의 다음 순열을 구해준다.
- prev_permutation은 현재 vector(또는 array)로 표현된 순열의 이전 순열을 구해준다.
- 위 함수의 인자로는 container의 시작과 끝 값이나 array의 시작과 끝 주소값을 넣는다.
- 순열이 있으면 true, 없으면 false 반환한다.

4. 이분 탐색(binary_search)
- 인자로 시작과 끝과 찾고자 하는 값을 넣는다.
- 찾고자 하는 값이 있으면 true, 없으면 false를 반환한다.

