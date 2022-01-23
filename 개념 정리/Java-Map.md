# Java-Map

Map 인터페이스를 구현한 Map 컬렉션 클래스들은 키와 값을 하나의 쌍으로 저장하는 방식(key - value 방식)을 사용한다.

- key(키) : 실직적인 value(값) 를 찾기 위한 이름의 역할을 한다



**map 의 특징**

- 요소의 저장 순서를 유지하지 않는다
- key : 중복을 허용 X
- value : 중복을 허용 O



**HashMap<Key, Value>**

- Map 컬렉션 클래스에서 가장 많이 사용되는 클래스 중 하나
- HashMap은 Map을 구현하고, key 와 value 를 묶어 하나의 entry 로 저장한다는 특징을 갖는다
- hash algorithm을 사용하여 많은 양의 데이터를 검색하는데 검색 속도가 매우 빠르다
- value 에 null 값도 가능하다
- 멀티쓰레드에서는 HashTable 을 사용한다 ( 값은 같을 다른 키로 저장하는 것은 가능)



**Hashtable<Key, Value>**

- HashMap 클래스와 같은 동작을 하는 클래스
- Hashtable 클래스는 HashMap 클래스와 마찬가지로 Map 인터페이스를 상속받는다
- 기존 코드와의 호환성을 위해서만 남아있으므로, Hashtable 클래스보다는 HashMap 클래스를 사용하는 것이 좋다



**HashMap<Key, Value>**

- 키와 값을 한 쌍으로 하는 데이터를 이진 검색 트리의 형태로 저장한다
- 이진 검색 트리는 데이터를 추가하거나 제거하는 등의 기본 동작 시간이 매우 빠르다
- TreeMap 클래스는 NavigableMap 인터페이스를 기존의 이진 검색 트리의 성능을 향상시킨 레드 블랙 트리로 구현한다
- Map 인터페이스를 구현하므로, 중복된 키로는 값을 저장 할 수 없다 (같은 값을 다른 키로 저장하는 것은 가능)