# Block_Chain<CR>
## The way the blockchain keeps security of datas.<CR>


### Hashing : Fast way of inserting, keeping datas. python_dictoinary -> hash table<CR>
### 해시 함수를 잘 짜도 충돌을 완벽하게 피할 수는 없다. -> 충돌 처리가 필요<CR>
#
## 충돌 처리
### 분리된 체인 : 연결리스트, 체인이 길어지면 검색이 느려지며, 추가적인 메모리가 필요<CR>
### 오픈 주소 해싱 : 추가적인 공간을 만들지 않고 기존에 해시 테이블 공간만으로 충돌을 해결 -> 주소를 다른 데이터에게 개방한다<CR>
### -> 선형 조사(탐사), 제곱 조사, 이중 해싱<CR>
#
### 선형 조사 : 충돌 발생 시, 해시 테이블의 다음 요소가 비어있는지 확인하고 저장, 추가적 메모리x, 한번 충돌시 주위에 충돌이 몰리는 군집화, 삭제가 복잡, 충돌 발생 시 마지막 요소 삭제<CR>
### 제곱 조사 : 선형 조사는 고정폭으로 다음 요소가 비었는지 확인, 제곱조사는 폭을 제곱으로 늘리면서 다음 요소가 비어있는지 확인, 군집화를 막음<CR>
#
### 이중 해싱 : 해싱 함수를 2개 만들어 충돌 시 2번째 함수 이용, 2번째 함수가 조사 시 이동 폭을 결정
#
## 암호학적 해시 함수 : hashlib
###패스워드 저장, 파일의 체크섬 확인
###update()에 bytes만 가능
#
##Standard of Blockchain
###1.hash
###2.making the blocks : 데이터와 이전 해시값을 합친 값을 해시함수에 넣어서 새 해시를 만듦. 연결리스트와 자료구조가 유사<CR>블록 : 데이터와 이전 해시값, 새 해시값을 합친 것<CR>일반적으로 다수의 거래내역을 묶어서 블록을 구성, 블록의 index, 시간 기록
###3.특수한 블록 제네시스 : 이전 해시값이 없는 특수한 블록
###블록체인 : 블록을 체인처럼 연결한 뒤, 네트워크 상의 노드들에 분산 저장하는 것
###4.블록을 검증
####현 블록의 이전 해시값과 이전 블록의 현 해시값 비교
####이전 블록의 해시값 재확인
####현 블록의 해시값 재확인
#
###블록체인은 유통 과정 등을 기록하는데 적당한 구조 : 유통과정, 시간을 블록체인에 기록하면 중간과정을 수정할 수 없다. -> 하지만, 전체, 특정 단계 이후의 조작은 가능
#
##PoW(Proof of Works, 작업 증명)
###블록을 만들 때 마지막으로 해싱을 하는데, 해싱이 어렵도록 하는 장치<CR> : 특정 조건의 해시값을 찾는다. 난이도가 추가되며, 검산할 때 사용된다. -> 블록에 nonce 항목을 추가해 nonce 값을 바꿔가면서 00으로 시작하는 해시값을 찾는다.


####*네트워크 관련 코딩은 없음. 추후 공부
