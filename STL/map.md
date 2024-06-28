# map
- map은 각 노드가 key와 value 쌍으로 이루어진 트리를 말한다(정확히 말하면 레드 블랙 트리).   
**중복은 허용하지 않는다.**
- 트리에 N개의 원소가 있을 때 O(logN)의 시간 복잡도를 가진다.

### include
- `#include <map>` C++ 코드에 include 가능하다.

### map 기본 형태
- `map<key, value> map1;` 가 기본 형태이다.
- 즉, key값을 이용해 value를 찾는다.

### 내부 함수
1. 삽입(insert)
- `map1.insert({"jeongu", 25})`
- 가장 기본적인 방법으로, key값은 중복이 허용되지 않는다.   
즉, 이미 가지고 있는 key의 데이터 삽입 시도는 무시된다.
- `map1["Dog"] = 3;`, 이런 식으로도 사용이 가능하다.

2. 인덱스 접근
- `map1["Dog"];`

3. 전체 순회
```cpp
for(auto itr = map1.begin(); itr != map1.end(); itr++){
    cout << itr->first << "" << itr->second << '\n';

}
// 향상된 for문
for(auto itr : map1){
    cout << p->first << " " << p->second << '\n';
}

or

for(pair<string, int> p : map1) {
        cout << p.first << " " << p.second << '\n';
}
```

4. 검색(find)
- 찾을 경우 true, 아니면 false
```cpp
if (map1.find("Alice") != map1.end()) {
	cout << "find" << endl;
}
else {
	cout << "not find" << endl;
}
```

5. 삭제(erase, clear)
```cpp
map1.erase("Alice");
map1.erase(m.begin()+2);
map1.erase(map1.begin(), map1.end()); // 전체 삭제
map1.clear(); // 전체 삭제
```

6. 크기(size)
- `map1.size();`, key의 개수를 반환한다.