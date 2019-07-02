# 티모소수

티모는 숫자놀이를 하던 도중 임의의 숫자에서 왼쪽부터 1자리, 2자리, 3자리...n자리 수를 추출했을 때, 추출한 모든 수가 소수인 수를 발견했다.
티모는 이 수들을 티모소수라고 이름 지었다. n이 주어졌을 때, n자리의 티모소수를 오름차순으로 정렬하여 출력하라.
예를 들어, 2333에서 왼쪽부터 1자리수는 2이고, 이 수는 소수이다. 왼쪽부터 2자리수는 23이고 이것 역시 소수이다.
이런 식으로 233과 2333도 소수이기 때문에, 2333은 출력해야 한다. 

입력
4

출력
2333
2339
2393
2399
2939
3119
3137
3733
3739
3793
3797
5939
7193
7331
7333
7393

```
첫 번째 숫자부터 만들고 DFS를 이용, 끝까지 소수판별하면서 전진
소수 판별식의 최적화를 해야 시간 초과를 방지할 수 있다. 소수판별 2부터 까지로 최적화하니 무난하게 통과.

이런 답을 예상 가능한 문제는 시간 걸리더라도 직접 노가다로 계산하는 프로그램을 만들어 답을 확인하자.

또한 숫자의 범위가 클 것이라 예상해 변수를 long으로 할당하면 시간초과가 났다. 대부분 int로 해결하자.

조합의수 이용, 카드 1 2 3 이 있으면
1 2 3 
```

# 카드놀이

숫자를 좋아하는 티모는 N개의 숫자 카드로 소수 만들기 게임을 즐겨한다.

게임 규칙은 다음과 같다.
소수를 만들 때 주어지는 숫자 카드들을 모두 사용하지 않아도 된다.
01, 001, 0001, 00...1 등은 같은 수로 취급한다.
카드는 0 ~ 9의 값을 가지며, 최대 카드 수는 7개다.
입력의 첫째 줄에 카드 수 N이 주어지고
둘째 줄에 N개의 카드 값이 주어질 때, 출력 가능한 모든 소수들을 오름차순 형태로 출력한다.
소수가 없을 경우 No Prime!을 출력한다.

입력
3
1 0 1

출력
11 101

입력
2
1 3

출력
3 13 31

```
조합의 문제. 카드 1, 2, 3주어지면
1개 뽑을 때 : 1 2 3
2개 뽑을 때 : 12 13 21 23 31 32
3개 뽑을 때 : 123 132 213 231 312 321

이런 가능한 수를 모두 생각해야 한다.

카드를 입력받으면 그 카드의 순서를 index 번호로 치환, 저 조합 index에 따라 숫자를 만들고,
그것이 소수인지 판별. 
이미 그 숫자가 답에 있으면 답에 추가하지 않음.

!!! 답이 없을 때 따로 출력해야 하는 부분을 구현하자. 빼먹으면 곤란하다!

테스트 케이스 4번 5번이 잘못되어서 그것 정정하자마자 바로통과.
```