# 싱글톤 패턴(Singleton pattern)

## 싱글톤 패턴이란

객체의 인스턴스가 오직 1개만 생성되는 패턴을 의미합니다.

즉, 어떠한 클래스(객체)가 유일한 인스턴스를 보유하게 하기 위한 개발 방법론입니다.

가령 객체의 인스턴스가 없다면 새로운 인스턴스를 만들고, 해당 인스턴스를 전역에서 공유합니다.

사실 Static(정적) 키워드와 비슷합니다.

## 왜 사용할까요?
가장 먼저는 메모리 측면에서 이점이 있습니다. 한번의 new 연산자를 통해서 고정된 메모리 영역을 사용하기 때문에 추후 해당 객체에 접근할 때 메모리 낭비를 방지할 수 있습니다.
또한, 재사용시에는 이미 있는 인스턴스를 부르는 것이기 때문에 속도 측면에서도 이점이 있습니다.

사실 가장 큰 목적은 데이터 공유입니다.

__단 주의해야할 점이 있습니다.__

1) 여러 클래스에서 싱글톤 인스턴스의 데이터에 동시에 접근한다면 동시성 문제가 발생할 수 있습니다.

2) 객체 지향에 위반되는 사례가 많습니다.



!동시성 문제 해결 방법 -> 멀티스레딩 환경에서 발생할 경우, syncronized 키워드 사용
## 싱글톤 패턴 사용법
1) default 생성자를 private 으로 막음

2) getInstance 메소드를 통해서 생성된 객체를 갖고 오거나, 없는 경우에는 새로 생성

    `public class SocketClient {

        private static SocketClient scoetClient = null;

        private SocketClient() {}

        public static SocketClient getInstance() {
            if(socketClient == null) {
                socketClient = new SocketClient();
            }
            return socketClient;
        }

        public void connect() {
            System.out.println("connect")
        }
    }`

## 싱글톤 패턴의 사용

* 어떠한 클래스(객체)가 유일하게 1개만 존재 할 때 사용
* 주로 자원을 공유할 때 사용
* 도메인 관점에서 인스턴스가 한 개만 존재하는 것을 보증하고 싶은 경우 사용
* TCP Socket 통신에서 서버와 연결된 Connect 객체에 주로 사용
-> 서버와 통신할 때, 요청마다 매번 연결하는 것이 아니고, 처음 연결했던 Connect 경로를 계속 사용해야함
* 스프링 Bean 객체들을 싱글톤으로 관리
-> 스프링의 빈 등록 방식은 기본적으로 싱글톤 스코프이고, 스프링 컨테이너는 모든 빈들을 싱글톤으로 관리합니다.