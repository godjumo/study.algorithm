
# ✔️[Lv. 1] [1845. 폰켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845)


문제 설명
-----

당신은 폰켓몬을 잡기 위한 오랜 여행 끝에, 홍 박사님의 연구실에 도착했습니다. 홍 박사님은 당신에게 자신의 연구실에 있는 총 N 마리의 폰켓몬 중에서 N/2마리를 가져가도 좋다고 했습니다.  

홍 박사님 연구실의 폰켓몬은 종류에 따라 번호를 붙여 구분합니다. 따라서 같은 종류의 폰켓몬은 같은 번호를 가지고 있습니다. 예를 들어 연구실에 총 4마리의 폰켓몬이 있고, 각 폰켓몬의 종류 번호가 [3번, 1번, 2번, 3번]이라면 이는 3번 폰켓몬 두 마리, 1번 폰켓몬 한 마리, 2번 폰켓몬 한 마리가 있음을 나타냅니다. 이때, 4마리의 폰켓몬 중 2마리를 고르는 방법은 다음과 같이 6가지가 있습니다.

1. 첫 번째(3번), 두 번째(1번) 폰켓몬을 선택
2. 첫 번째(3번), 세 번째(2번) 폰켓몬을 선택
3. 첫 번째(3번), 네 번째(3번) 폰켓몬을 선택
4. 두 번째(1번), 세 번째(2번) 폰켓몬을 선택
5. 두 번째(1번), 네 번째(3번) 폰켓몬을 선택
6. 세 번째(2번), 네 번째(3번) 폰켓몬을 선택

이때, 첫 번째(3번) 폰켓몬과 네 번째(3번) 폰켓몬을 선택하는 방법은 한 종류(3번 폰켓몬 두 마리)의 폰켓몬만 가질 수 있지만, 다른 방법들은 모두 두 종류의 폰켓몬을 가질 수 있습니다. 따라서 위 예시에서 가질 수 있는 폰켓몬 종류 수의 최댓값은 2가 됩니다.  

당신은 최대한 다양한 종류의 폰켓몬을 가지길 원하기 때문에, 최대한 많은 종류의 폰켓몬을 포함해서 N/2마리를 선택하려 합니다. N마리 폰켓몬의 종류 번호가 담긴 배열 nums가 매개변수로 주어질 때, N/2마리의 폰켓몬을 선택하는 방법 중, 가장 많은 종류의 폰켓몬을 선택하는 방법을 찾아, 그때의 폰켓몬 종류 번호의 개수를 return 하도록 solution 함수를 완성해주세요.

### 제한사항

* nums는 폰켓몬의 종류 번호가 담긴 1차원 배열입니다.
* nums의 길이(N)는 1 이상 10,000 이하의 자연수이며, 항상 짝수로 주어집니다.
* 폰켓몬의 종류 번호는 1 이상 200,000 이하의 자연수로 나타냅니다.
* 가장 많은 종류의 폰켓몬을 선택하는 방법이 여러 가지인 경우에도, 선택할 수 있는 폰켓몬 종류 개수의 최댓값 하나만 return 하면 됩니다.

---

### 입출력 예

| nums | result |
| --- | --- |
| [3,1,2,3] | 2 |
| [3,3,3,2,2,4] | 3 |
| [3,3,3,2,2,2] | 2 |

### 입출력 예 설명

입출력 예 #1  

문제의 예시와 같습니다.

입출력 예 #2  

6마리의 폰켓몬이 있으므로, 3마리의 폰켓몬을 골라야 합니다.  

가장 많은 종류의 폰켓몬을 고르기 위해서는 3번 폰켓몬 한 마리, 2번 폰켓몬 한 마리, 4번 폰켓몬 한 마리를 고르면 되며, 따라서 3을 return 합니다.

입출력 예 #3  

6마리의 폰켓몬이 있으므로, 3마리의 폰켓몬을 골라야 합니다.  

가장 많은 종류의 폰켓몬을 고르기 위해서는 3번 폰켓몬 한 마리와 2번 폰켓몬 두 마리를 고르거나, 혹은 3번 폰켓몬 두 마리와 2번 폰켓몬 한 마리를 고르면 됩니다. 따라서 최대 고를 수 있는 폰켓몬 종류의 수는 2입니다.



<details>
  <summary><h2>내 풀이(언어)</h2></summary>
  
  ### 정답 코드

  ```python
  def solution(nums):
    select_num = len(nums) // 2
    nums = set(nums)
    if len(nums) >= select_num:
        return select_num
    else:
        return len(nums)
  ```

  **풀이과정**
  
  1. 전체 N 마리 중 절반(N/2)를 선택할 수 있음
  2. 가장 많은 종류를 선택하는 경우를 찾아 종류 개수를 반환해야함, 경우의 수는 따지지 않음
  3. 즉 최대 N/2 종류만큼 고를 수 있다는 의미이므로 종류가 N/2보다 크면, 전체 종류를 선택하지 못한다는 의미이므로 N/2 종류 만큼 고르면 됨
  4. 종류가 N/2보다 적다면, 전체 종류를 선택하고도 선택 횟수가 남는다는 의미이므로 모든 종류를 고르면 됨

  ---
  <div align=center>
  <img width="597" alt="스크린샷 2024-12-22 오후 5 44 40" src="https://github.com/user-attachments/assets/ba53616d-49f3-4d62-9c54-69f00f17e63f" />
  </div>
  
  ### 풀이에 대한 고찰

  단순한 로직이라서 크게 어렵지 않았다. 역시 Lv. 1인가..  
  예전에 처음 풀 때는 좀 어렵게 풀었던거 같은데 로직짜는게 조금은 성장했나??  

  ## 다른 사람 풀이


  ### 코드
  ```python
  def solution(ls):
    return min(len(ls)/2, len(set(ls)))
  ```
  ### 설명
  나는 if문을 사용했지만 여기서는 코드라인을 더 줄이기 위해 min을 사용했다.  
  나도 좀 더 적극적으로 min, max를 사용해야지..

  ### 출처
  [프로그래머스 다른사람 풀이](https://school.programmers.co.kr/learn/courses/30/lessons/1845/solution_groups?language=python3)

  ## 회고
  딱히.. 필요가 없다 그렇게 어려운 문제가 아니라서.. 기본기나 굳은 뇌를 풀어준다는 느낌으로 풀고 지나가자
</details>
<br>
<span style="color:gray"> #해시 </span>
