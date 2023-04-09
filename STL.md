# STL

표준 템플릿 라이브러리 또는 STL은 C++ 표준 라이브러리의 일부인 소프트웨어 라이브러리입니다. C++ 개발자가 쉽게 데이터 구조를 조작하고 다양한 알고리즘을 수행할 수 있도록 하는 몇 가지 일반 클래스와 함수를 제공합니다. STL의 주요 구성 요소는 다음과 같습니다.

- 컨테이너: 벡터, 목록, 대기열, 스택 및 세트와 같은 동일한 유형의 여러 요소를 보유하는 데이터 구조입니다.
- 알고리즘: 정렬, 검색, 병합 등 컨테이너에 대한 다양한 작업을 수행하는 기능입니다.
- 반복자: 컨테이너의 요소를 순차적으로 통과하는 방법을 제공하는 개체입니다.
- 할당자: 컨테이너 요소에 대한 메모리 할당 및 할당 해제 방법을 제어하는 개체입니다.
- 함수 개체: 함수로 호출할 수 있는 개체로, 사용자가 STL 알고리즘과 함께 사용할 사용자 지정 작업을 만들 수 있습니다.



### 컨테이너

컨테이너는 C++의 표준 템플릿 라이브러리(STL)의 핵심 구성 요소입니다. 객체 컬렉션을 저장하고 관리하도록 설계된 데이터 구조로, 포함된 요소와 상호 작용할 수 있는 인터페이스를 제공합니다. 컨테이너는 크게 시퀀스 컨테이너와 연관 컨테이너의 두 가지 유형으로 분류할 수 있습니다.

1. 시퀀스 컨테이너: 시퀀스 컨테이너는 요소의 순서가 중요한 선형 방식으로 요소를 저장합니다. 여기에는 다음이 포함됩니다.

   - `vector`: 인접한 메모리 블록에 요소를 저장하는 동적 배열입니다. 인덱스를 사용하여 요소에 대한 빠른 액세스를 제공하고 요소가 추가되거나 제거될 때 자동으로 크기가 조정됩니다. 벡터는 요소에 대한 임의 액세스와 컨테이너 끝에서 일정한 시간 삽입 또는 삭제가 필요할 때 유용합니다.

   - `list`: 목록 내의 모든 위치에서 일정한 시간 삽입 및 삭제를 허용하는 이중 연결 목록. 목록은 컨테이너 중간에 요소를 자주 삽입하거나 삭제해야 할 때 유용하지만 벡터에 비해 요소 액세스가 느립니다.

   - Deque(Double-ended queue): 벡터와 리스트의 요소를 결합한 하이브리드 컨테이너. 요소에 대한 빠른 임의 액세스를 허용하고 컨테이너의 시작과 끝 모두에서 일정한 시간 삽입 및 삭제를 지원합니다.

   - 정방향 목록: 목록 내의 모든 위치에서 일정한 시간 삽입 및 삭제를 허용하지만 단방향 순회만 지원하는 단일 연결 목록입니다. 이중 연결 목록보다 적은 메모리를 사용하며 다음과 같은 경우에 유용합니다.

2. 연관 컨테이너는 키를 기반으로 비선형 방식으로 요소를 저장하는 C++ 표준 템플릿 라이브러리(STL)의 컨테이너 범주입니다. 연관 컨테이너의 요소는 키에 따라 정렬 및 구성되므로 효율적인 검색, 삽입 및 삭제 작업이 가능합니다. 연관 컨테이너에는 다음이 포함됩니다.

   * Set:   집합은 고유한 요소를 정렬된 순서로 저장하는 컨테이너입니다. 각 요소는 자체 키 역할을 하며 세트의 두 요소는 동일할 수 없습니다. 집합은 일반적으로 이진 검색 트리(예: Red-Black 트리와 같은 균형 트리) 또는 해시 테이블로 구현됩니다. 

   * Multiset:   다중 집합은 집합과 유사하지만 동일한 요소의 여러 인스턴스를 허용합니다. 요소는 여전히 정렬된 순서로 저장되지만 중복이 허용됩니다. 집합과 마찬가지로 다중 집합은 일반적으로 이진 검색 트리 또는 해시 테이블로 구현됩니다. 

   * Map:   맵은 키를 기준으로 정렬된 순서로 키-값 쌍을 저장하는 연관 컨테이너입니다. 각 키는 고유해야 하며 특정 값과 연결됩니다. 맵은 종종 사전 또는 조회 테이블을 구현하는 데 사용되며 일반적으로 이진 검색 트리 또는 해시 테이블로 구현됩니다. 

   * Multimap:   멀티맵은 맵과 유사하지만 동일한 키를 가진 여러 키-값 쌍을 허용합니다. 키-값 쌍은 키를 기준으로 정렬된 순서로 저장되지만 중복 키는 허용됩니다. 맵과 마찬가지로 멀티맵은 일반적으로 이진 검색 트리 또는 해시 테이블로 구현됩니다.



### 알고리즘

알고리즘은 컨테이너 및 해당 요소에 대해 다양한 작업을 수행하는 일반 함수 집합입니다. 특정 요구 사항을 충족하는 모든 컨테이너 유형과 함께 작동하도록 설계되어 매우 다양하고 재사용이 가능합니다. 가장 일반적인 STL 알고리즘 중 일부는 다음 범주로 그룹화할 수 있습니다.



1. 정렬 알고리즘: 이러한 알고리즘은 컨테이너 내에서 특정 순서로 요소를 정렬하는 데 사용됩니다. 예를 들면 다음과 같습니다.

   - `sort`: 기본적으로 오름차순 또는 사용자 정의 비교 함수에 따라 주어진 범위의 요소를 정렬합니다.

   - `stable_sort`: 동일한 경우 상대적인 순서를 유지하면서 주어진 범위의 요소를 정렬합니다.

   - `partial_sort`: 요소를 부분적으로 정렬하여 가장 작은 요소 또는 가장 큰 요소가 최종 정렬 위치에 있는지 확인합니다.



2. 검색 알고리즘: 이러한 알고리즘은 컨테이너 내의 특정 요소 또는 범위를 검색하는 데 사용됩니다. 예를 들면 다음과 같습니다.

   - `find`: 요소 범위에서 주어진 요소를 검색합니다.

   - `binary_search`: 정렬된 범위 내에서 특정 요소에 대한 이진 검색을 수행합니다.

   - `lower_bound` 및 `upper_bound`: 주어진 요소가 정렬된 순서를 위반하지 않고 삽입될 수 있는 첫 번째 위치와 마지막 위치를 각각 찾습니다.



3. 수정: 이러한 알고리즘은 컨테이너의 내용 또는 구조를 수정합니다. 예를 들면 다음과 같습니다.

   - `copy`: 한 범위에서 다른 범위로 요소를 복사합니다.
   - `move`: 소스 범위를 지정되지 않은 상태로 두고 한 범위에서 다른 범위로 요소를 이동합니다.
   - `fill`: 주어진 범위의 모든 요소에 특정 값을 할당합니다.
   - `replace`: 지정된 값의 모든 항목을 지정된 범위 내의 다른 값으로 바꿉니다.
   - `reverse`: 주어진 범위에서 요소의 순서를 반대로 바꿉니다.
   - `rotate`: 요소를 주기적으로 이동하면서 지정된 오프셋만큼 범위의 요소를 회전합니다.

   

4. 분할 알고리즘: 이러한 알고리즘은 특정 조건 또는 술어에 따라 컨테이너의 요소를 재정렬합니다. 예를 들면 다음과 같습니다.

   - `partition`: 요소가 다음을 충족하도록 범위의 요소를 재정렬합니다.