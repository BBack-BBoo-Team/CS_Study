# Java Stream API의 특징은 무엇이 있나요?

## Java Stream API 란?

Java 8에서 추가된 기능으로, 배열이나 컬렉션 요소를 람다식으로 처리하기 위한 API입니다.

## 특징

1. 내부 반복을 통해 작업을 수행하고, 이로 인해서 코드가 간결해집니다.
2. 재사용이 불가능합니다.
3. 원본 데이터를 변경하지 않고, 복서해서 사용합니다.
4. 필터-맵 기반의 API를 사용하여, 지연 연산을 통해 성능을 최적화합니다.
5. 병렬 처리를 지원합니다.
6. 데이터를 추상화하여, 데이터 종류와 상관 없이 같은 방식으로 데이터를 처리할 수 있습니다.

## 중개 연산 메소드
* 필터링 : filter(), distinct()
* 변환 : map(), flatMap()
* 제한 : limit(), skip()
* 정렬 : sorted()
* 연산 결과 확인 : peek()

## 최종 연산 메소드
* 출력 : forEach()
* 소모 : reduce()
* 검색 : findFirst(), findAny()
* 검사 : anyMatch(), allMatch(), noneMatch()
* 통계 : count(), min(), max()
* 연산 : sum(), average()
* 수집 : collect()
