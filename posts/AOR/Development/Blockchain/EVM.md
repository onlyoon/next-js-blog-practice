#aor 
### Ethereum Virtual Machine
>[!note]
>#### 이더리움 가상 머신
>
>>스마트 컨트랙트의 배포, 실행 그리고 상태변경을 처리한다.

### 코드 변환 단계
- Solidity(고수준 언어) 코드가 Bytecode로 컴파일 되고 이것을 EVM 이 직접 해석한다.
![](../../../Stuff/Image/AOR/Blockchain/Pasted%20image%2020231207151353.png)

### EVM 구조
- PC (Program Counter)
	- 실행되는 명령어 주소 저장
- Virtual ROM
	- Smart Contract 코드 임시 저장 장소
- Gas Available
	- 거래 비용 && 수수료 보관소
	- 명령어가 실행되기 전에 수수료가 없을 경우, Tx시작 전의 상태로 되돌림 
- Stack
	- 명령어 실행의 입/출력 데이터가 저장되는 곳 (1024개의 아이템 저장 장소)
- Memory
	- 명령어 실행 중 데이터 저장 & 함수에 인수 전달
- Storage
	- Smart Contract 전역 변수 저장
![](../../../Stuff/Image/AOR/Blockchain/Pasted%20image%2020231207151610.png)
>[!info]
>>EVM은 다양한 프로그래밍 언어로 구현되며 자바스크립트와 연관된 구현된 EVM은 [ethereumjs-vm](https://github.com/ethereumjs/ethereumjs-monorepo)을 참고하라.


- https://ethereum.org/en/developers/docs/evm/
### [Blockchain](../../Dev-Index/Blockchain.md) Index로 돌아가기