# 개미수열

개미수열은 소설가 베르나르베르베르의 소설 개미로 알려진 수열로 아래와 같은 방식으로 이루어져있다.

1
11
12
1121
122111

첫째 줄은 1로 시작하며 다음 줄 부터는 윗 줄에 숫자를 세는 것이다.
그렇기에 2번째 줄부터는 1이 1개, 3번째 줄은 1이 2개 4번째 줄은 1이 1개 2가 1개.... 
이렇게 나아가는 방식이다. n이 주어지면 n번째 줄의 개미수열을 출력하라.


입력
4

출력
1121

```
개미수열부분은 인터넷에서 따왔다.

입력이 40까지 나오기 때문에 매우 큰 배열을 만들어야한다.
```

# 아나그램

 문자를 바꾸어 나열할 수 있는 모든 가능성을 구하는 것을 '아나그램(anagram)'이라고 한다. 예를 들어 cat의 아나그램은 다음과 같다. 
cat cta act atc tca tac
한 단어의 아나그램의 총수는 그 단어의 문자수의 팩토리얼이다. 한 단어를 입력했을 때 그 단어의 아나그램을 출력하시오.
아나그램의 순서는 입력된 단어의 문자 순서에 따라야 한다.(출력하는 단어의 최대 개수는 100으로 제한한다.) 
또한, 한 문자열을 두 번 이상 출력하지 않는다.(중복 없이 출력)

입력으로 하나의 단어가 주어지는데, 영어 소문자로만 구성되어 있다.
입력된 단어에 대해 조건에 맞게 아나그램 리스트를 출력한다.

입력
cat

출력
cat cta act atc tca tac

입력
catt

출력
catt ctat ctta actt atct attc tcat tcta tact tatc ttca ttac

```
백준 6443번문제가 나왔다. DFS로 푸는 방법을 이용해 풀어봤으나 TEST CASE 2번을 통과 못했다.

기존 입력받은 인풋을 abc순서로 바꿔준다. 바꾼 단어를 가지고 DFS를 돌린다. 
만들어진 단어와 같은 기존에 이미 만들어진 단어가 있는지 확인, 없으면 단어 벡터에 넣는다. 

그리고 100개까지만 출력한다.
인풋을 abc순서로 바꾸는 것을 구현하는 것이 복잡하다.

abca의 경우 맨 앞 a와 맨 끝 a가 같은문자가 아니라 각각의 우선순위 1,2,3,4를 부여하는것으로 봐야한다.
이부분 TREAT부분 anagram만드는부분을 수정해야한다.
```