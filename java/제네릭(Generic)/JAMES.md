# 제네릭 (Generic)

## 제네릭(generic) 이란?

제네릭(generic)이란 데이터 타입을 일반화한다는 것입니다.

자바에서 개발을 한다면, 변수를 선언할 때 타입을 명시해줘야 합니다.

명시해준 변수는 형변환을 하지 않은 이상 해당 타입을 유지해야합니다.

반면, 제네릭 타입을 선언한다면 데이터 타입을 명시하지 않아도 됩니다.

즉, 상황에 따라 유연하게 변수를 활용할 수 있게 됩니다.

이러한 제네릭은 특정 변수에만 지정할 수 있는 것은 아닙니다.

정확하게는 클래스나 인터페이스 또는 메서드 내부에서 사용될 데이터 타입을 지정하는 것입니다.

제네릭이 사용되는 클래스 중 대표적인 예로는 Collection Framework 의 클래스들이 있습니다.

가령 List 인터페이스 내부에 꼭 문자열 데이터만 저장될 일은 없습니다. 어떠한 경우에는 정수 또는 Boolean 타입의 데이터가 저장되어 있을 수 있습니다.

즉, 상황에 따라 저장되는 타입이 다릅니다.

이러한 이유 때문에 제네릭이 사용됩니다.


## 사용법

1. 클래스 또는 인터페이스를 설계할 때 클래스명 옆에 `<T>` 작성합니다.

`class ExGeneric<T> {

    private T t;

    public void setT(T t) {
        this.t = t;
    }

    public T getT() {
        return t;
    }
}`

`public <K, V> void getPrint(K k, V v) {
    System.out.println(k +"," + v);
}`

2. 이렇게 설계한 클래스를 사용하는 곳에서 파라미터(<>) 안에 타입을 지정합니다.

`ExGeneric<String> exGeneric = new ExGeneric<String>()`
`ExGeneric<String> exGeneric = new ExGeneric<>() // java 7 부터 생략 가능`

-> exGeneric 객체의 필드 변수와 메서드에 T를 작성한 부분엔 String 타입이 적용됩니다.

3. 입력 매개변수 값만으로 제네릭 타입이 유추되면 타입 생략 가능

## 타입 매개변수

<> 을 다이아몬드 연산자라고 합니다. <> 안에 하나의 대문자로 표현합니다.

* <T> | Type
* <E> | Element
* <K> | Key
* <N> | Number
* <V> | Value
* <R> | Result

### 와일드 카드 <?>
* <?> : 타입 매개변수에 모든 타입 사용
* <? extends T> : T 타입과 T 타입을 상속받는 하위 클래스 타입만 사용
* <? super T> : T 타입과 T 타입을 상속하는 상위 클래스 타입만 사용
