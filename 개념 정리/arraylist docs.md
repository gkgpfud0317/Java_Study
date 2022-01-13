공용 클래스 ArrayList<E>
extends abstractList <E>
implements List<E> 랜덤 액세스, 복제 가능, 일련화 가능 구현
목록 인터페이스의 크기 조정 가능한 array 구현

모든 선택적 목록 작업을 구현하고 null을 포함한 모든 요소를 허용

이 클래스는 목록 인터페이스를 구현하는 것 외에도 목록을 저장하는 데 내부적으로 사용되는 배열의 크기를 조작하는 방법을 제공

(이 클래스는 동기화되지 않았다는 점을 제외하면 Vector와 거의 동일)
크기는 비어 있음, 가져오기, 설정, 반복기 및 listIterator 작업이 일정한 시간 내에 실행

추가 작업은 상각된 상수 시간, 즉 요소를 추가하는 데 O(n) 시간이 필요 

다른 모든 작업은 선형 시간(대략적으로 말해서)에 따라 실행

LinkedList 구현에 비해 상수 계수는 낮음

각 ArrayList 인스턴스에는 용량이 있음

- 용량은 목록의 요소를 저장하는 데 사용되는 어레이의 크기
- 항상 적어도 목록 크기만큼 큼
- 요소가 어레이 목록에 추가되면 용량이 자동으로 증가
- 성장 정책의 세부 사항은 요소를 추가하는 데 상각된 시간 비용이 일정하다는 사실 이외에는 명시 X

애플리케이션은 용량 보장 작업을 사용하여 많은 수의 요소를 추가하기 전에 어레이 목록 인스턴스의 용량을 늘릴 수 있음. 이렇게 하면 증분 재할당의 양을 줄일 수 있음

이 구현은 동기화되지 않음. 여러 스레드가 ArrayList 인스턴스에 동시에 액세스하고 스레드 중 하나 이상이 목록을 구조적으로 수정하는 경우 목록을 외부에서 동기화해야 함 (구조 수정은 하나 이상의 요소를 추가하거나 삭제하거나 명시적으로 백업 어레이의 크기를 조정하는 작업이며, 요소의 값만 설정하는 것은 구조가 아님) 이 작업은 일반적으로 목록을 자연스럽게 캡슐화하는 일부 개체에서 동기화하여 수행 이러한 개체가 없으면 컬렉션을 사용하여 목록을 "포장되어"야 함Collections . synchronizedList 메서드. 이 방법은 실수로 목록에 동기화되지 않은 액세스를 방지하기 위해 생성 시 수행하는 것이 가장 좋음



```
List list = Collections . synchronizedList(new ArrayList( . . . ) );
```

이 클래스의 반복기 및 listIterator 메서드에 의해 반환되는 반복기는 fail-fast임. 반복기 생성 후 언제든지 목록이 구조적으로 수정되는 경우, 반복기 자체의 제거 또는 추가 방법을 통하지 않는 한 반복기가 Concurrent ModificationException을 생성

따라서, 동시 수정에 직면하여, 반복자는 미래의 결정되지 않은 시간에 자의적이고 비결정적인 행동을 감수하기 보다는 빠르고 깨끗하게 실패

일반적으로 비동기화된 동시 수정이 존재하는 상태에서는 어떠한 하드 보증도 할 수 없기 때문에 반복기의 fail-fast 동작을 보장할 수 없음. 장애 속도 반복자가 동시 수정 실행최선의 노력을 기울인다는 예외. 그러므로, 이 예외의 정확성을 위해 이 예외에 의존하는 프로그램을 작성하는 것은 잘못된 일이 될 것이다: 반복자의 빠른 동작은 버그를 감지하는 데만 사용되어야 한다.

이 클래스는 Java Collections Framework의 멤버입니다.



**필드 요약**

java.util 클래스에서 상속된 필드.추상 목록

modCount



**생성자 요약**

생성자

ArrayList() : 초기용량이 10인 빈 목록을 생성

ArrayList(Collection <? extend E> c) : 지정된 컬렉션의 요솔르 컬렉션의 반복자가 반환하는 순서대로 포함하는 목록을 구성

ArrayList(int initialCapacity) : 지정된 초기 용량을 가진 빈 목록을 생성



**메소드 요약**

| boolean         | add(E e)                                   | 지정된 요소를 이 목록의 끝에 추가                            |
| --------------- | ------------------------------------------ | ------------------------------------------------------------ |
| void            | add(int index, E element)                  | 이 목록의 지정된 위치에 지정된 요소                          |
| boolean         | addAll(Collection<? extends E> c)          | 지정된 컬렉션의 반복기에서 반환되는 순서대로 지정된 컬렉션의 모든 요소를 이 목록의 끝에 추가 |
| boolean         | addAll(int index, Collection<? extend E>c) | 지정된 위치에서 시작하여 지정된 컬렉션의 모든 요소를 이 목록에 삽입 |
| void            | clear()                                    | 이 목록에서 모든 요소를 제거                                 |
| Object          | clone()                                    | 이 ArrayList 인스턴스의 복사본을 반환                        |
| boolean         | contain(Object o)                          | 이 목록에 지정된 요소가 포함되어 있으면 true를 반환          |
| void            | ensureCapacity(int minCapacity)            | 최소 용량 인수에 의해 지정된 요소 수 이상을 포함할 수 있도록 필요한 경우 이 ArrayList 인스턴스의 용량을 늘림 |
| void            | forEach(Consumer<? super E> action)        | 모든 요소가 처리되거나 작업이 예외를 발생시킬 때까지 반복 가능한 각 요소에 대해 지정된 작업을 수행 |
| E               | get(int index)                             | 이 목록의 지정된 위치에 있는 요소를 반환                     |
| int             | index0f(object o)                          | 이 목록에서 지정된 요소의 첫 번째 발생 인덱스를 반환하거나, 이 목록에 요소가 없는 경우 -1을 반환 |
| boolean         | isEmpty()                                  | 이 목록에 요소가 없으면 true를 반환                          |
| Iterator<E>     | iterator()                                 | 이 목록의 요소 위에 올바른 순서로 반복기를 반환              |
| int             | lastIndex0f(object o)                      | 이 목록에서 지정된 요소의 마지막 발생 인덱스를 반환하거나, 이 목록에 요소가 없는 경우 -1을 반환 |
| ListIterator<E> | ListIterator()                             | 이 목록의 요소 위에 목록 반복기를 반환(적절한 순서로)        |
| ListIterator<E> | ListInterator(int index)                   | 목록의 지정된 위치에서 시작하여 이 목록의 요소에 대해 적절한 순서로 목록 반복기를 반환 |
| E               | remove(int index)                          | 이 목록에서 지정된 위치의 요소를 제거                        |
| boolean         | remove(Object o)                           | 지정된 요소가 있는 경우 이 목록에서 첫 번째 항목을 제거      |
| boolean         | removeAll(Collection<?> c)                 | 지정된 컬렉션에 포함된 모든 요소를 이 목록에서 제거          |
| boolean         | removeIf(Predicate<? super E> filter)      | 지정된 술어를 충족하는 이 컬렉션의 모든 요소를 제거          |
| protected void  | removeRange(int fromIndex, int toIndex)    | 인덱스가 Index(색인 포함) 및 Index(색인 제외) 사이에 있는 모든 요소를 이 목록에서 제거 |
| void            | replaceAll(UnaryOperator<E> operator)      | 이 목록의 각 요소를 해당 요소에 연산자를 적용한 결과로 대체  |
| boolean         | retainAll(Collection<?> c)                 | 지정된 컬렉션에 포함된 이 목록의 요소만 유지                 |
| E               | set(int index, E element)                  | 이 목록의 지정된 위치에 있는 요소를 지정된 요소로 바꿈       |
| int             | size()                                     | 이 목록의 요소 수를 반환                                     |
| void            | sort(Comparator<? super E> c)              | 지정된 비교기에 의해 유도된 순서에 따라 이 목록을 정렬       |
| Spliterator<E>  | spliterator()                              | 이 목록의 요소 위에 늦은 바인딩 및 실패 속도 분할자를 생성   |
| List<E>         | sublist(int fromIndex, int toIndex)        | 지정된 Index(포함)와 Index(배타적) 사이의 이 목록 부분 보기를 반환 |
| Object[]        | toArray()                                  | 이 목록의 모든 요소를 포함하는 배열을 올바른 순서(첫 번째 요소부터 마지막 요소까지)로 반환 |
| <T> T[]         | toArray(T[] a)                             | 이 목록의 모든 요소가 포함된 어레이를 올바른 순서(첫 번째 요소부터 마지막 요소까지)로 반환합니다. 반환되는 어레이의 런타임 유형은 지정된 어레이의 런타임 |
| void            | trimTosize()                               | 이 ArrayList 인스턴스의 용량을 목록의 현재 크기로 자름       |




