---
title: "Feecc의 데모"
description: 이 강좌는 Feecc 시스템 및 그 구성 요소를 알아보는 데 관한 것입니다.
metaOptions: [배우기, Feecc에 익숙해지기]
defaultName: Getting Used to Feecc
---

<RoboAcademyText fWeight="500">
이 레슨에서는 Feecc의 기본 기능을 가상 테스트베드를 사용하여 실제 생산 추적 시스템의 예시를 흉내 내는 것으로 테스트할 것입니다.
</RoboAcademyText>

데모 목적으로 레이블 인쇄나 비디오 녹화와 같은 일반적인 기능은 제외되어 있지만, 이 시스템의 주요 개념을 갖고 있습니다.

## 필수 조건

데모를 실행하려면 다음이 필요합니다:

- UNIX와 유사한 시스템 ([Ubuntu 22.04.2](https://releases.ubuntu.com/jammy/)에서 테스트됨)
- [Docker](https://docs.docker.com/engine/install/ubuntu/) 및 [Docker compose](https://docs.docker.com/compose/)
- 웹 브라우저 (Google Chrome 및 Mozilla Firefox에서 테스트됨)

## 설치

다음 명령을 실행하세요:

<LessonCodeWrapper language="bash">
git clone https://github.com/Multi-Agent-io/feecc-academy
cd feecc-academy
sudo docker compose up -d --build
</LessonCodeWrapper>

작동 중인 컨테이너를 확인하려면 다음을 실행하세요:

<LessonCodeWrapper language="bash">
sudo docker ps -a
</LessonCodeWrapper>

다음 출력이 표시되어야 합니다:

<LessonCodeWrapper language="bash" codeClass="big-code" noLines noCopyIcon>
CONTAINER ID   IMAGE                               COMMAND                  CREATED          STATUS                             PORTS     NAMES
0db8382bb271   feecc-academy-workbench-daemon      "uvicorn app:app --h…"   19 seconds ago   Up 7 seconds (healthy)                       feecc_academy_workbench_daemon
0dbc7bb977d1   feecc-academy-workbench-frontend    "node nodeServer.js"     20 seconds ago   Up 19 seconds (health: starting)             feecc_academy_workbench_frontend
a74fa229eb90   robonomics/robonomics:sha-bd71a23   "robonomics --dev --…"   20 seconds ago   Up 19 seconds (health: starting)             feecc_academy_robonomics_node
0c9e8022658a   mongo:jammy                         "docker-entrypoint.s…"   20 seconds ago   Up 19 seconds (healthy)                      feecc_academy_mongoDB
6b0748904d0f   ipfs/go-ipfs:v0.17.0                "/sbin/tini -- /usr/…"   20 seconds ago   Up 19 seconds (healthy)                      feecc_academy_ipfsnode
814e6f489a77   nyurik/alpine-python3-requests      "tail -f /dev/null"      20 seconds ago   Up 19 seconds                                feecc_academy_hid_emulator
</LessonCodeWrapper>

## 데모 시작

1. 브라우저에서 http://localhost:3000/로 이동하면 환영 화면이 표시됩니다.

2. 이 단계에서 시스템은 직원에게 권한 부여를 위해 RFID 카드를 스캐너에 놓도록 요청해야 합니다. 데모에서는 권한 부여를 위해 `hid-emulator.py`를 사용할 수 있습니다. 이를 위해 별도 Docker 컨테이너를 실행하세요:

<LessonCodeWrapper language="bash">
sudo docker exec -ti feecc_academy_hid_emulator sh
python3 hid-emulator.py
</LessonCodeWrapper>

RFID 카드를 제공하고 바코드를 스캔하는 두 가지 기능을 흉내 낼 수 있습니다. 첫 번째 기능이 필요하므로 `1`을 입력하세요.

<LessonCodeWrapper language="bash" codeClass="big-code" noLines noCopyIcon>
> Select emulated action (1/2): 
>  1. Put ID card on the RFID 스캐너.
>  2. Scan a sample barcode with a barcode scanner.
> 1
> INFO:2023-03-21 21:42:05,370:Event relayed to endpoint http://127.0.0.1:5000/workbench/hid-event
</LessonCodeWrapper>

3. 화면을 볼 수 있습니다. 구성 유형을 선택하려면 `단일 장치`를 선택하십시오.

<LessonImages src="feecc-course/menu.png" alt="Feecc start menu"/>

4. 고유 ID가 생성된 장치에서 작업을 시작하는 것을 나타내는 알림이 왼쪽 하단 모서리에 나타납니다. 파란색 알림은 가상 프린터의 활동도 표시합니다. 실제 설정에서는 장치의 ID가 있는 바코드가 이 순간에 인쇄됩니다.

<LessonImages src="feecc-course/single_device.png" alt="Single device composition"/>

5. `구성 시작`을 클릭하여 장치 조립 과정을 녹화하기 시작하십시오. 필요한 모든 조립 단계를 거쳐야하며, 직원이 단계를 완료하면 `다음` 버튼을 클릭한 후 비디오가 IPFS에 저장됩니다. 조립을 일시 중지(`일시 중지`)하여 나중에 돌아오거나 프로세스를 완전히 중지(`중지`)할 수도 있습니다.

6. 모든 조립 단계가 완료되면 `완료` 버튼이 나타납니다. 그 후 Feecc는 장치 인증서를 저장하는 것을 제안합니다. 그러나 이 작업을 수행하기 전에 브라우저에서 [로컬 Robonomics 노드](https://polkadot.js.org/apps/?rpc=ws%3A%2F%2F127.0.0.1%3A9944#/explorer)를 열어야합니다. 나중에 필요할 것입니다. 그 후 Feecc로 돌아가 `여권 저장`을 클릭하십시오.
    
    화면 모서리에 새로운 알이 표시됩니다: 인증서가 Robonomics 및 IPFS에 업로드되었음을 나타내는 알림 및 인증서로 이어지는 봉인 태그 및 QR 코드를 인쇄하는 두 개의 파란색 메시지가 표시됩니다.

<LessonImages src="feecc-course/single_certificate.png" alt="Cetrificate of single composition"/>

7. Robonomics 로컬 노드 화면의 `Chain info` 섹션에서 `최근 이벤트` 열 아래에 `datalog.NewRecord`라는 새 이벤트가 표시됩니다. 확장하면 장치의 인증서 파일에 해당하는 IPFS CID가 `바이트` 필드에 표시됩니다.

<LessonImages src="feecc-course/single_datalog.png" alt="Datalog of single composition"/>

인쇄된 QR 코드에는 이 CID로 연결된 링크가 포함되어 있어 브라우저에서 인증서 파일을 열 수 있습니다. 로컬 IPFS 노드에서 그 파일을 찾을 수 없을 수 있으므로 `localhost:8080/ipfs/CID`로 파일에 로컬로 액세스할 수 있습니다. 인증서의 내용은 다음과 같습니다:

<LessonCodeWrapper language="json" codeClass="big-code" noLines noCopyIcon>
Unit Unique Code: 423d3c1b42f6427e80cc881a16e07451
Unit Model Name: Single Device
Total Assembly Time: 0:05:37
Production Stages:
- Name: Prepare Tools (not finished.)
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 17:38:47
  Finish Time: 26-06-2023 17:40:28
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Prepare Tools (not finished.)
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 17:40:30
  Finish Time: 26-06-2023 17:42:06
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Prepare Tools
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 17:42:16
  Finish Time: 26-06-2023 17:43:00
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Saw Through the Single Device
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 17:43:00
  Finish Time: 26-06-2023 17:43:51
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Stack Tools
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 17:43:51
  Finish Time: 26-06-2023 17:44:36
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
</LessonCodeWrapper>

8. 이제 여러 장치로 구성된 복합 조립을 위한 인증서를 만들어 보겠습니다. 유형 선택 메뉴에서 `복합 장치`를 클릭한 다음 `샘플 장치`를 클릭하십시오. (구성 번호 필드에 위치한) 단위 ID를 복사하십시오. 나중에 필요할 것입니다. 그런 다음 장치 조립의 표준 단계를 진행하십시오.

9. 조립 후 `복합 장치`로 돌아가 `최종 조립`을 눌러 복합 조립을 완료하십시오. 시스템은 조립된 장치의 단 ID를 제공하라고 요청할 것입니다. 직원은 바코드를 스캔해야합니다. 이 프로세스를 시뮬레이션하려면 `hid-emulator.py`로 돌아가 바코드 스캔을 위해 함수 `2`를 선택하고 저장된 단위 ID를 삽입하십시오.

10. 다음으로 시스템은 복합 조립의 필요한 단계를 거치고 인증서를 생성할 것입니다.

<LessonCodeWrapper language="json" codeClass="big-code" noLines noCopyIcon>
Unit Unique Code: d08101feae7c4efbb5529885c9ad544b
Unit Model Name: Composite Device
Total Assembly Time: 0:00:03
Production Stages:
- Name: Prepare Tools
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 18:18:25
  Finish Time: 26-06-2023 18:18:26
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Tape the Sample Device to the base plate
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 18:18:26
  Finish Time: 26-06-2023 18:18:27
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
- Name: Stack Tools
  Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
  Start Time: 26-06-2023 18:18:27
  Finish Time: 26-06-2023 18:18:28
  Assembly data in IPFS: This is a place for any production data, let it be video
    record, some sensor data or any other data collection representing the production
    process.
Unit Components:
- Unit Unique Code: b165b382c3674127a6aaf5817c5a7040
  Unit Model Name: Sample Device
  Total Assembly Time: 0:00:03
  Production Stages:
  - Name: Prepare Tools
    Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
    Start Time: 26-06-2023 18:17:45
    Finish Time: 26-06-2023 18:17:46
    Assembly data in IPFS: This is a place for any production data, let it be video
      record, some sensor data or any other data collection representing the production
      process.
  - Name: Assemble Sample Device
    Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
    Start Time: 26-06-2023 18:17:46
    Finish Time: 26-06-2023 18:17:47
    Assembly data in IPFS: This is a place for any production data, let it be video
      record, some sensor data or any other data collection representing the production
      process.
  - Name: Stack Tools
    Employee Code: e9b69b302f72d82ca47964196536aab3f36e367910aff06d2be30888f9ad4234
    Start Time: 26-06-2023 18:17:47
    Finish Time: 26-06-2023 18:17:48
    Assembly data in IPFS: This is a place for any production data, let it be video
      record, some sensor data or any other data collection representing the production
      process.
Total Assembly Time (Including Components): 0:00:06
</LessonCodeWrapper>

11. 데모를 삭제하려면 명령을 입력하십시오:

<LessonCodeWrapper language="bash">
sudo docker compose down --rmi all && docker builder prune -f
</LessonCodeWrapper>

<RoboAcademyText fWeight="500">
다음 레슨에서는 Feecc 시스템의 모든 필수 구성 요소를 실제로 배포하는 방법을 진행하겠습니다.
</RoboAcademyText>