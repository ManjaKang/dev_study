# 튜플

C++에서 튜플은 서로 다른 유형의 여러 값을 단일 개체로 함께 저장할 수 있는 유형입니다. 튜플은 관련 데이터를 함께 그룹화한다는 점에서 구조체 및 클래스와 유사하지만 더 가볍고 특정 사용 사례에 더 편리할 수 있습니다.

튜플은 "std::tuple" 템플릿 클래스와 튜플에 저장될 값의 유형을 사용하여 정의할 수 있습니다. 예를 들어 다음과 같이 정수, 문자열 및 부울 값을 저장하는 튜플을 정의할 수 있습니다.

```cpp
#include <tuple>

using namespace std;

tuple<int, string, bool> myTuple(10, "hello", true);
```



### 엑세스

튜플이 정의되면 "std::get" 함수를 사용하여 해당 값에 액세스할 수 있으며 검색하려는 값의 인덱스가 뒤따릅니다. 예를 들어 다음과 같이 "myTuple" 튜플에서 문자열 값을 검색할 수 있습니다.

```cpp
std::string strVal = std::get<1>(myTuple);
```

구조적 바인딩을 사용하면 튜플에 저장된 값을 보다 간결하고 읽기 쉬운 방식으로 별도의 변수로 풀 수 있습니다. 튜플과 함께 구조적 바인딩을 사용하려면 튜플 값과 동일한 유형의 변수를 선언하고 "std::tie" 함수를 사용하여 해당 튜플 값에 변수를 바인딩합니다. 예를 들어:

```cpp
#include <tuple>
#include <iostream>

int main() {
  std::tuple<int, std::string, bool> myTuple(10, "hello", true);
  
  auto [intVal, strVal, boolVal] = myTuple;
  
  std::cout << intVal << std::endl;    // output: 10
  std::cout << strVal << std::endl;    // output: hello
  std::cout << boolVal << std::endl;   // output: 1
}
```

