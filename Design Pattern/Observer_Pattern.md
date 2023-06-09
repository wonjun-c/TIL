# Observer Pattern

<img src="./img/observer.jpg">

## 정의
```
- 일대다(one-to-many)관계를 정의.
- 한 객체의 상태가 변경되면 그 객체에 의존하는 모든 객체에 연락이 간다.
```

## 사용된 원칙
```
1~3.
4. 상호작용하는 객체 사이는 느슨하게 결합해야 한다 (Loose Coupling).
```

## 문제상황과 해결
```
문제 : 기상 스테이션
- 기상 스테이션에서 WeatherData 보내주면 현재 기상 조건을 보여주는 디스클레이를 만들어야한다.
- 현재 조건, 기상 통계, 기상 예측 3가지의 디스플레이 장비에서 정보를 갱신해가며 보여줘야한다.
- WeatherData 내에서 데이터가 갱신되면 각 디스플레이에 update를 하게 해보았다.
- 디스플레이가 추가/제거 될경우 프로그램을 고쳐야 한다.

해결
- 날씨 정보를 주제(Subject)로 두고, 디스플레이를 옵저거(Observer)로 두자.
- 주제가 달라지면 연결된 모든 옵저버에게 그 소식이 전해진다.
- 주제가 옵저버에 대해 아는것은 특정 인터페이스를 구현한다는 것 뿐이다.
- 즉 상호작용을 하지만 서로에 대해 잘 모르는 '느슨한 결합'이다.
- 옵저버는 언제든지 추가/제거가 가능하고 이때 주제를 변경할 필요가 없다.
- 서로 독립적으로 사용가능하고 바뀌더라도 서로에게 영향을 주지 않는다.

```

## Example
```
유튜브 구독을 생각해보자.
유튜브는 채널을 구독할수 있는 시스템이 있다.
채널을 구독하면 채널에 새로운 소식들이 생기면 알람등의 정보가 구독자들에게 온다.
적게는 몇천, 많게는 수백만의 구독자들이 있는 채널도 많다. 이런 채널에서 구독자들에게
새로운 정보를 전달해야 한다고 하면, 유튜브 채널에서 수백만의 구독자들을 관리하는 것은
매우 어려울 것이다. 이때 옵저버 패턴을 사용한다면, 채널에서는 새로운 정보를 보내기만
하면되고 구독자들에 관한 것은 신경 쓰지 않아도 될 것이다. 구독자가 늘어나거나 줄어드는 것도
신경쓰지 않아도 될것이다.
```


## 자바 내장 옵저버 패턴
