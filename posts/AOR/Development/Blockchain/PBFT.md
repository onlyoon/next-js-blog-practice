#aor 
### PBFT(Practical Byzantine Fault Tolerance)
>[!note]
>#### 프랙티컬 비잔틴 장애허용
>
>>BFT를 속도와 실용적인 측면에서 개선한 형태이다.
>
>>비동기 네트워크에서 배신자 노드가 f개 있을 경우, 총 노드의 갯수가 `3f + 1` 이상이면 해당 네트워크의 합의는 신뢰적임을 수학적으로 증명한 알고리즘
>
>>Private Blockchain에서 가장 신뢰할 수 있는 합의 알고리즘이다.
>
>>시간 복잡도가 O(n^2)으로 높은 지연시간을 지녔다.

>[!warning]
>>왜 3f + 1갯수 이상일 경우 신뢰적일까?

#### 공식
$$n = 3f + 1$$
$$n = 전체 노드 수$$
$$f = 비잔틴 노드 수$$
#### 3-Phase Protocol
![](Stuff/Image/AOR/Blockchain/Pasted%20image%2020231004140037.png)
- `Request` 단계
	- PBFT는 클라이언트로부터 요청을 받은 이후에 3단계 프로토콜을 실시한다.
1. `PrePreare` 단계
	- 요청을 처음 받은 노드(`Primary Node`)는 다른 백업 노드들에게 준비를 하라고 `<PrePrepare, v, n, D(m)σp`메세지 발송
1. `Prepare` 단계
	- 백업 노드들이 각자 받은 `PrePrepare`메세지를 검증한 뒤, 검증 완료된 메세지를 다른 노드들에게 Broadcast하며, 동시에 각기 다른 노드들로부터 `2f`개의 메세지(`prepared certificate`)를 수집한다.
2. `Commit` 단계
	- 백업 노드들이 `prepared certificate`를 지니면 `<Commit, v, n, i>σp` 메세지를 모든 노드들에게 Broadcast하며, 동시에 각기 다른 노드들로부터 `2f + 1`개의 메세지(committed certificate)를 수집한 후 메세지를 클라이언트에게 보낸다.
- `reply` 단계
	- 클라이언트가 모든 노드들로부터 `committed certificate`를 받으면, 결과를 확인하고 종료한다. 
#### View Change Protocol
![](Stuff/Image/AOR/Blockchain/Pasted%20image%2020231004140738.png)
- 클라이언트로부터 처음 요청 받는 노드(`Primary Node`)의 실패를 방지하기 위한 백업 `Primary Node`를 선출하는 프로토콜
- `Primary Node`가 실패인 경우 `View-Change`메세지를 전송한다.
	- `Primary Node`가 클라이언트로부터 요청을 받고 시간이 지나도, 메세지를 보내지 않을 경우
	- 클라이언트의 첫 `reply`실패 이후, 재실패시, `Primary Node` 의심
- `View-Change`메세지
	- 
### [Blockchain](AOR/Dev-Index/Blockchain.md) Index로 돌아가기