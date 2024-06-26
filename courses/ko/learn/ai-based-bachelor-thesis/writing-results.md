---
title: "쓰기: 결과"
description: AI 도구를 활용하여 학사 논문 빠르게 시작하기
metaOptions: [AI 도구를 활용하여 학사 논문 빠르게 배우기]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
학사 논문 결과를 처리하는 부분은 일반적으로 시각적인 부분인데, 여기서는 특정 지표를 그래프와 표로 시각화하고 이러한 결과에 대한 토론이 포함됩니다. AI 도구가 이 작업을 돕는 데 도움이 될까요? 당연히 그렇지만 약간의 세부 사항이 있습니다.
</RoboAcademyText>

## 데이터 표현 및 변환

아마도 AI 어시스턴트가 가장 잘 처리하고 제시하는 것은 원시 데이터일 것입니다. 이전 가이드에서 AI를 사용하여 UML 다이어그램을 성공적으로 만들었지만, 일반적으로 구조화된 데이터 배열은 통계를 이용하여 다이어그램이나 표로 쉽게 변환될 수 있습니다. 예를 들어, ChatGPT는 스마트 홈의 로보노믹스 파라체인의 원시 데이터를 기반으로 [Subscan](https://robonomics.subscan.io/)에서 시간별로 성공적인 데이터로그 트랜잭션의 수를 계산하고 분배하는 작업을 수행했습니다. 여기 결과의 일부가 있습니다:

| Hour  | Successful Transactions | Total Transactions | Percentage of Success |
|-------|-------------------------|--------------------|-----------------------|
| 13:00 | 4                       | 4                  | 100%                  |
| 14:00 | 5                       | 5                  | 100%                  |
| 15:00 | 6                       | 6                  | 100%                  |
| 16:00 | 5                       | 5                  | 100%                  |
| 17:00 | 5                       | 5                  | 100%                  |
| 18:00 | 6                       | 6                  | 100%                  |

ChatGPT는 시간당 트랜잭션 수를 세는 것뿐만 아니라 그들의 백분율을 유도했습니다. 

## 심층 분석

그러나 AI에게 비구조화된 데이터를 기반으로 더 심층적인 분석을 요청면 어떨까요? 불행히도, 여기서 우리가 이미 겪은 문제가 시작됩니다: 맥락 제한과 환각. 예를 들어, 이전에 만든 스마트 홈의 홈 어시스턴트의 로그 파일을 가져와서 ChatGPT에게 다음 요청을 했습니다:

<RoboAcademyDialog>

Based this logs of smart home system, write section called "Analysis of IoT Hub Logs" in 1000 words. Add precise statistics of occurrences of found events and recommendations for solution of found problems.

</RoboAcademyDialog>

로그는 대략 다음과 같습니다 (총 500 줄의 로그):

<LessonCodeWrapper language="bash" noCopyIcon noLines codeClass="big-code">
    2023-05-29 14:17:18.301 DEBUG (MainThread) [custom_components.robonomics] Time changed: 2023-05-29 14:17:18.299347+00:00
    2023-05-29 14:17:18.309 DEBUG (MainThread) [custom_components.robonomics.get_states] Start getting info about dashboard and services
    2023-05-29 14:17:18.321 DEBUG (SyncWorker_0) [custom_components.robonomics.ipfs] Getting last file hash from /ha_robonomics_config with prefix config-
    2023-05-29 14:17:18.341 DEBUG (SyncWorker_0) [custom_components.robonomics.ipfs] Last /ha_robonomics_config file config-1685367962.12049, with hash QmbQ4STfozcCPeHpKkcrH26hNTnupU1o4LD1JQTFWKpran
    2023-05-29 14:17:18.352 DEBUG (SyncWorker_10) [custom_components.robonomics.ipfs] Read data from local file: /ha_robonomics_config/config-1685367962.12049
    2023-05-29 14:17:19.439 DEBUG (MainThread) [custom_components.robonomics.get_states] Got states to send datalog
    2023-05-29 14:17:21.469 DEBUG (SyncWorker_9) [custom_components.robonomics.ipfs] Time from the last pin: 1:07:04.863542
    2023-05-29 14:17:21.469 DEBUG (SyncWorker_9) [custom_components.robonomics.ipfs] Telemetry must not be pinned
    2023-05-29 14:17:21.471 DEBUG (SyncWorker_1) [custom_components.robonomics.ipfs] Getting last file hash from /ha_robonomics_telemetry with prefix None
    2023-05-29 14:17:21.491 DEBUG (SyncWorker_1) [custom_components.robonomics.ipfs] Last /ha_robonomics_telemetry file data-1685369332.9767303, with hash QmNY2kPBA4Xi2L2DjTWzqhRk5BXS5KyDqjvtYb8mcA43mx
    2023-05-29 14:17:21.492 DEBUG (SyncWorker_4) [custom_components.robonomics.ipfs] Start adding /tmp/data-1685369841.445844 to local node, pin: False
    2023-05-29 14:17:21.631 DEBUG (SyncWorker_4) [custom_components.robonomics.ipfs] File /tmp/data-1685369841.445844 was added to local node with cid: QmdmmUXEvmtW1UnttcEDhc8pee8CwVdEFH4aax9XZj76m8
    2023-05-29 14:17:21.692 DEBUG (SyncWorker_4) [custom_components.robonomics.ipfs] File data-1685369332.9767303 with was unpinned
    2023-05-29 14:17:27.165 DEBUG (SyncWorker_6) [custom_components.robonomics.ipfs] Actual balance in crust network - 604385098
    2023-05-29 14:17:28.617 DEBUG (SyncWorker_6) [custom_components.robonomics.ipfs] approximate cost to store the file - 1000067848
    2023-05-29 14:17:28.617 WARNING (SyncWorker_6) [custom_components.robonomics.ipfs] Not enough account balance to store the file in Crust Network
    2023-05-29 14:17:28.634 DEBUG (MainThread) [custom_components.robonomics.robonomics] Send datalog states request, another datalog: False
    2023-05-29 14:17:28.638 DEBUG (SyncWorker_0) [custom_components.robonomics.robonomics] Start creating rws datalog
    2023-05-29 14:17:55.573 DEBUG (SyncWorker_0) [custom_components.robonomics.robonomics] Datalog created with hash: 0x396f26a5e3fdaa89910e7f78491f90150d6f9e59e9c7e85f6b9d090ade235077
    2023-05-29 14:19:40.007 WARNING (MainThread) [custom_components.local_luftdaten.sensor] REST request error: Cannot connect to host 192.168.13.141:80 ssl:default [연결 call failed ('192.168.13.141', 80)]

</LessonCodeWrapper>

응답으로, AI 도구는 종종 환각을 시작하여, 분명히 다른, 존재하지 않는 데이터에 대한 분석을 제안했습니다:

<RoboAcademyDialog>

<ChatGPT/>

The logs revealed a significant number of connectivity issues encountered by the IoT devices. Out of a total of 10,000 recorded events, 1,200 (12%) were related to connectivity problems.

...

The analysis identified a notable number of unauthorized access attempts to the smart home system. Approximately 300 (3%) events were logged, indicating potential security breaches. These attempts could lead to unauthorized control or access to sensitive information within the smart home.

...

The logs revealed a lack of regular firmware updates for the IoT devices, with only 20 (0.2%) events indicating successful updates. This finding raises concerns regarding the security and performance of the devices.

</RoboAcademyDialog>

다른 경우에는 AI가 맥락을 잃었습니다. 예를 들어, Subscan 트랜잭션 로그에 대한 다음 요청이 있었습니다:

<RoboAcademyDialog>

Analyze the logs below and tell me what kind of Smart Home System analysis can be done on them. These are the transaction logs for the SUB_CONTROLLER address received from the Robonomics parachain, related to the subscription IoT.

</RoboAcademyDialog>

학사 논문의 맥락과 스마트 홈 온라인 강좌의 텍스트를 AI에게 다시 제공했음에도 불구하고, AI는 단순히 로그에 존재하지 않는 데이터로 오해할 수 있는 답변을 생성했습니다:

<RoboAcademyDialog>

<ChatGPT/>

User Behavior Analysis:

Analyzing the logs provided insights into user behavior within the Smart Home System. By examining the transaction details, we observed the following user behavior patterns:
- Most Frequently Used Features: Lighting control was the most frequently used feature, accounting for 45% of total transactions. Temperature control followed closely with 30% of total transactions, while security system monitoring and appliance automation accounted for 15% and 10% respectively.
- Usage Patterns: Users tended to interact with the Smart Home System more frequently during weekdays compared to weekends. This suggests that the system is primarily utilized for regular daily activities, such as lighting and temperature control, rather than special occasions or leisure activities.

</RoboAcademyDialog>

전반적으로, 결과 섹션을 작성하는 데 AI 어시스턴트를 사용하는 것은 성공보다는 실패로 간주될 수 있습니다. 네, AI는 데이터를 제시하고 처리하는 데 도움을 줄 수 있지만 본질적으로는 클래식 데이터 과학 도구와 비교했을 때 아주 조금의 시간을 절약할 뿐입니다. 게다가 사용자들은 제공된 답변의 정확성을 항상 걱정하고 두 번 확인해야 합니다.

<RoboAcademyText fWeight="500">
Now we can move on to the final section of our bachelor's thesis — Conclusions, where we will not only finish writing the thesis, but also make overall conclusions on the use of AI for this purpose.
</RoboAcademyText>