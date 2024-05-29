# 과제
### 초콜릿 자르기
정화는 N×M 크기의 초콜릿을 하나 가지고 있다. 초콜릿은 금이 가 있는 모양을 하고 있으며, 그 금에 의해 N×M개의 조각으로 나눠질 수 있다.

초콜릿의 크기가 너무 크다고 생각한 그녀는 초콜릿을 친구들과 나눠 먹기로 했다. 이를 위해서 정화는 초콜릿을 계속 쪼개서 총 N×M개의 조각으로 쪼개려고 한다. 초콜릿을 쪼갤 때에는 초콜릿 조각을 하나 들고, 적당한 위치에서 초콜릿을 쪼갠다. 초콜릿을 쪼갤 때에는 금이 가 있는 위치에서만 쪼갤 수 있다. 이와 같이 초콜릿을 쪼개면 초콜릿은 두 개의 조각으로 나눠지게 된다. 이제 다시 이 중에서 초콜릿 조각을 하나 들고, 쪼개는 과정을 반복하면 된다.

초콜릿을 쪼개다보면 초콜릿이 녹을 수 있기 때문에, 정화는 가급적이면 초콜릿을 쪼개는 횟수를 최소로 하려 한다. 초콜릿의 크기가 주어졌을 때, 이를 1×1 크기의 초콜릿으로 쪼개기 위한 최소 쪼개기 횟수를 구하는 프로그램을 작성하시오.
```
n, m = map(int, input().split())
a = (n * m) - 1
print(a)
```
### 손가락 게임
손가락 게임은 두 플레이어가 동시에 손가락을 일정 개수 펴서 특정 표식을 만들어 상성을 겨루는 게임이다. 플레이어는 
$0$개의 손가락을 펴서 '바위' 표식(즉, 손가락을 피지 않은 상태), 
$2$개의 손가락을 펴서 '가위' 표식, 
$5$개의 손가락을 펴서 '보' 표식을 만들 수 있다. 이 외의 개수의 손가락을 피면 '무효' 표식을 만든 것으로 간주한다.

두 플레이어 모두 같은 표식을 낼 경우 승패를 가릴 수 없으며, 표식에 따른 상성은 아래와 같다.

'무효' 외의 다른 표식을 낸 플레이어는 '무효'를 낸 플레이어를 상대로 승리한다.
'바위'를 낸 플레이어는 '가위'를 낸 플레이어를, '가위'를 낸 플레이어는 '보'를 낸 플레이어를, '보'를 낸 플레이어는 '바위'를 낸 플레이어를 상대로 승리한다.
준성과 익준은 손가락 게임을 진행하려고 한다. 두 사람이 핀 손가락의 개수를 보고 승패를 판별해 주도록 하자.


```
#include <stdio.h>

int a, b;

int main() {
   
    scanf("%d %d", &a, &b);

    if (a == 3 || a == 4) a = 1;
    if (b == 3 || b == 4) b = 1;

    if (a == b) printf("=");
    else if (a == 1) printf("<");
    else if (b == 1) printf(">");
    else if (a == 0 && b == 2) printf(">");
    else if (a == 2 && b == 5) printf(">");
    else if (a == 5 && b == 0) printf(">");
    else printf("<");

    return 0;
}
```
### 과민성 대장 증후군
상원이는 과민성 대장 증후군을 앓고 있다. 과민성 대장 증후군의 원인은 스트레스!

상원이의 
$N$일 동안의 스트레스 변화량 
$A_1,\cdots ,A_N$이 주어진다. 
$A_i\ge 0$ 이면 
$i$번째 날에 
$A_i$ 만큼 스트레스가 쌓이고, 
$A_i<0$ 이면 
$i$번째 날에 
$-A_i$ 만큼 스트레스가 해소된다. 단, 변화를 관찰하기 시작한 시점의 스트레스 양은 
$0$이며, 누적된 스트레스 양보다 해소하는 스트레스 양이 더 많을 경우 스트레스는 
$0$이 될 때까지만 감소한다.

상원이는 스트레스가 
$M$ 이상 쌓인 날에 복통을 겪게 될 때, 상원이가 며칠 동안 복통에 시달리게 되는지 알아보자.
```
#include <stdio.h>

int main() {
    int n, m;
    scanf("%d %d", &n, &m);

    int s = 0;
    int p = 0;
    int c;
    
    for(int i = 0; i < n; i++) {
        scanf("%d", &c);
        s += c;
        if(s < 0){
            s = 0;
        }else if(s >= m){
            p++;
    }
    }

    printf("%d\n", p);
    return 0;
}
```
### 버블버블
민구는 원소의 개수가 
$N$개이고 값이 서로 다른 정수 배열 
$A$를 오름차순으로 만들고 싶다.

배열의 
$i$번째 원소와 
$i+1$번째 원소끼리 서로 위치를 바꿀 수 있고, 정렬 과정 중 언제든지 최대 딱 한 번 배열 전체의 순서를 뒤집을 수 있다.

원소를 교환하는 것, 배열 전체를 뒤집는 것 모두 
$1$번의 횟수로 계산한다.

주어진 배열 
$A$를 오름차순으로 만드는데 필요한 최소한의 횟수를 구하여라.
```
#include <stdio.h>

void reverse(int* arr, int n) {
    for (int i = 0; i < n / 2; i++) {
        int temp = arr[i];
        arr[i] = arr[n - i - 1];
        arr[n - i - 1] = temp;
    }
}

int bubbleSort(int* arr, int n) {
    int count = 0;
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                count++;
            }
        }
    }
    return count;
}

int isSorted(int* arr, int n) {
    for (int i = 1; i < n; i++) {
        if (arr[i - 1] > arr[i]) {
            return 0;
        }
    }
    return 1;
}

int main() {
    int n;
    scanf("%d", &n);
    
    int arr[n], ac[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        ac[i] = arr[i];
    }
    
    int tmdnlcl = bubbleSort(arr, n);
    
    reverse(ac, n);
    int dlrpanj = bubbleSort(ac, n) + 1;
    
    int result = tmdnlcl < dlrpanj ? tmdnlcl : dlrpanj;
    
    printf("%d\n", result);
    
    return 0;
}
```
### 밤양갱

민우는 비비의 신곡 <밤양갱>에 꽂혀 하루 종일 "달디달고 달디달고 달디달고... 달디단"이 머릿속을 맴돌고 있다.

민우의 머릿속에선 daldidalgo가 총 
$N$번 반복된 후, 반복이 완료되었다면 daldidan으로 끝나게 된다. 예를 들어 
$N=3$이라면 민우의 머릿속엔 daldidalgodaldidalgodaldidalgodaldidan이 재생된다.

민우는 
$N$이 주어지면 얼마나 빨리 daldidalgodaldidalgo...daldidan을 컴퓨터에 입력할 수 있는지 궁금하다. 매초 민우는 두 개의 작업 중 하나를 선택하여 시행할 수 있다.

알파벳 소문자 a부터 z 중에서 민우가 원하는 알파벳을 하나 골라서 지금까지 입력한 내용의 맨 뒤에 입력한다.
지금까지 입력한 문자열의 연속된 부분 문자열을 복사 후 입력한 내용의 맨 뒤에 붙여넣는다. 예를 들어 지금까지 작성한 문자열이 ajouapcshake라면, ajouapcshake를 복사할 수도, apc를 복사할 수도 있지만, aashake를 복사하여 붙여넣을 수는 없다.
민우는 몇 초 만에 머릿속에 떠오른 가사를 컴퓨터에 입력할 수 있을까?
```
n = int(input())
a,count = 1,1

while a < n+1:
    a += a
    count += 1
print(8+count)
```


