# Calculator_Clone

## 아이폰의 기본 계산기 클론 코딩

---

## 05/29

### 구현사항/문제

- 기본적인 UI 구성 완료 `VStack`, `HStack` 과 `Geometry`를 이용하여 만들었다.

> 하다가 도중에 그리드라는 개념을 알았는데, 이미 뒤엎기는 그래서 그냥 진행 하였음. 그리드에 관해서는 따로 찾아봐야겠다...

- % 연산, 양수/음수 만드는 연산을 구현 하였으나, 매우 작은 수에서 음수로 입력하면 0으로 출력 되는 문제가 있어서 내일 해결 해볼 듯 하다. 아마도 `Double`형을 `String`으로 변환하는 과정 중에서 분기를 잘못 나눈것 같은 생각이 든다.

- 지우는 기능(AC) 구현 중, 숫자를 입력하거나 연산을 입력받으면 Bool로 체크해서 문자를 C로 바꾸는 기능과, 내부 분기 조금 나누면 완성하지 싶다

- 숫자의 지수 표기법(e.g. 1.2e10, 2.4e-9 ...) 구현, 세자리 마다 쉼표 구현, 소수점 입력 구현, 최대 숫자의 입력 개수는 9개로 제한을 두어 구현하였다. (기본 앱과 동일하게 하기 위함) `NumberFormatter` 를 사용하였다.

### 아쉬운점

#### Grid의 미사용, 형변환 미숙

위에도 적었지만, `Grid`로 구성했으면 어땠을까 라는 아쉬움이 있고, 입력을 받고 결과를 보여주는 과정에서 `Double` 과 `String`의 변환은 필수 불가결이라고 생각하는데 구현을 할 때 입력은 `String` 으로 받아서 내부에서 `Double`로 변환 후, 다시 보여주는 부분을 `String`으로 변환을 또 하였는데, 이 과정에서 좀 에러가 생기는 듯 하다.

#### enum, switch 미활용

기능을 구현하면서 도중에 느꼈지만, 꽤 여러가지 조건으로 분기를 나눠야해서 `switch`와 `enum`을 활용하면 더 좋았을 듯 하다. 사용해 본적이 많이 없다보니 생각도 나지 않았던 점이 아쉽다.

#### class, struct ViewModel, Model 개념 미숙

지금 모델이라고 파일을 지정해서 기능과 데이터를 몰아 넣었는데, 계산기라서 그나마 좀 다행이라고 생각하지만 실제로 데이터를 여기에 넣는 방식은 좋지 않았던것 같다. 원본이 변경될 여지가 있으니 데이터는 `Model`을 따로 만들어서 구조체 내부에서 조작을 하는게 좋았을듯 하다. 아직은 정확히 잘 모르기 때문에 더 공부를 해야하지 싶다. (이런 조언을 해주신 익명의 S군께 감사,,)

---
