---
title: "강의 #6, 로봇공학 통합 설정"
lastUpdate: Thu May 18 2023 10:46:29 GMT+0400 (Samara Standard Time)
description: 홈 어시스턴트 코스
lessonNumber: 7
metaOptions: [로보노믹스와 홈 어시스턴트를 활용한 주권 스마트 홈 배우기]
defaultName: Sovereign Smart Home with Robonomics and Home Assistant
---


## 이것은 무엇에 관한 것입니까

이 레슨에서는 홈 어시스턴트에 Robonomics를 추가하고 구독과 연결된 계정을 만듭니다. 이 통합을 통해 홈 어시스턴트가 Robonomics 파라체인 기능을 사용할 수 있게 되며, 먼저 암호화된 스마트 홈 데이터를 탈중앙화된 클라우드로 전송할 수 있습니다.


## 이론

귀하의 스마트 홈 데이터는 <code>datalog</code> 팔렛에서 <code>record()</code> extrinsic를 사용하여 블록체인에 암호화된 장치 데이터를 저장할 수 있습니다. 

보다 정확히 말하면, 이 통합은 데이터를 저장하기 위해 IPFS를 사용하고, 그런 다음 IPFS 해시를 datalog extrinsic로 전송하여 블록체인에 저장합니다. 그러나 이 기능은 IoT 구독을 통해 호출되기 때문에 전체 기능은 다음과 같이 보입니다: <code>rws.call(datalog.record(YOUR_IPFS_HASH))</code>.

## 지침

<List type="numbers">

<li>

홈 어시스턴트에 Robonomics 추가

<List>

<li>

홈 어시스턴트의 웹 인터페이스에서 <code>Settings</code>-><code>Device & Services</code>로 이동하고 <code>ADD INTEGRATION</code>을 누릅니다. <code>Robonomics</code>를 검색합니다.

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/QmQp66J943zbF6iFdkKQpBikSbm9jV9La25bivKd7cz6fD', type:'mp4'}]" />

</li>

<li>

Robonomics를 클릭하고 구성을 입력합니다: 

\- <code>SUB_CONTROLLER</code> 계정에서 관리자 계정 시드를 추가합니다

\- 이전에 만든 <code>SUB_OWNER</code> 계정의 공개 주소를 구독 소유자 주소로 추가합니다

\- 데이터 전송 간격을 설정합니다 (기본값은 10분입니다)

\- (선택 사항) Pinata 핀 서비스의 자격 증명을 추가하여 데이터를 IPFS 네트워크 전체에 더 널리 퍼뜨릴 수 있습니다

</li>

<li>

구성을 완료한 후 <code>SUBMIT</code>을 누릅니다. 모든 것을 올바르게 입력했다면 성공 창이 표시됩니다.

</li>
</List>
</li>

<li>

로보노믹스 Dapp에서 사용자 추가하기 

<List>

<li>

스마트 홈 장치를 제어할 홈 어시스턴트를 위해 별도의 사용자를 만들어야 합니다. 이전에 만든 계정을 사용할 수 없습니다. 왜냐하면 <code>SUB_OWNER</code> 및 <code>SUB_CONTROLLER</code>가 보안을 제공하며, 홈 어시스턴트를 처음 시작할 때 만든 첫 번째 사용자는 로보노믹스 파라체인 계정이 없기 때문입니다.

</li>

<li>
이전 레슨에서 했던 것처럼 로보노믹스 파라체인에 계정을 만들기 시작하세요.
</li>

<li>

[dapp](https://dapp.robonomics.network/#/subscription/devices)에서 구독에 이 계정을 추가하세요. 이제 액세스 목록에 <code>SUB_OWNER</code>, <code>SUB_CONTROLLER</code> 및 <code>USER</code> 세 개의 주소가 있어야 합니다.

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/QmSxzram7CF4SXpVgEyv98XetjYsxNFQY2GY4PfyhJak7H', type:'mp4'}]" />

</li>

<li>

[홈 어시스턴트 계정](https://dapp.robonomics.network/#/home-assistant)이라는 dapp 서비스로 이동하세요. 방금 만든 계정을 오른쪽 사이드바에서 선택하세요 (원하는 계정을 선택했는지 프로필 아이콘을 눌러 확인하세요).

필요한 필드에 <code>USER</code> 시드를 입력하세요. 관리자 크레딧 필드에 <code>SUB_OWNER</code> 및 <code>SUB_CONTROLLER</code> 주소를 추가하요. 모든 것이 올바르다면 확인 상태 <code>VERIFIED</code>를 볼 수 있을 것입니다.

</li>

<li>

방금 등록한 새 사용자를 위해 비밀번호를 만들고, 이제 구독으로 인해 수수료 없이 거래를 확인하세요. 나중에 <code>복원</code> 탭에서 비밀번호를 복원할 수 있습니다.

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/QmW2TXuwCYXzgcRfEUx4imZU5ZerEzkuD5P53u9g2WnxDh', type:'mp4'}]" />

</li>

<li>

등록 프로세스가 완료되면 사용자 주소로 로그인하여 새로 만든 비밀번호로 홈 어시스턴트에 로그인하세요. 이제 로보노믹스 Dapp을 사용하여 집을 제어할 수 있습니다.

</li>
</List>
</li>
</List>