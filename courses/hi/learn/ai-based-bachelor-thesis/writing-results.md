---
title: "लेखन: परिणाम"
description: एआई-संचालित उपकरणों के साथ अपने स्नातक थीसिस को शीघ्र प्रारंभ करें
metaOptions: [सीखें, एआई-संचालित उपकरणों के साथ अपने स्नातक थीसिस को शीघ्र प्रारंभ करें]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
स्नातक की थीसिस के परिणामों को संसाधित करने के लिए समर्पित अनुभाग में आमतौर पर एक प्रदर्शनात्मक भाग होता है, जहां आप ग्राफ़ और तालिकाओं पर कुछ संकेतकों की कल्पना करते हैं, साथ ही इन परिणामों की चर्चा भी करते हैं। क्या AI उपकरण इस कार्य में मदद कर सकते हैं? उत्तर स्पष्ट रूप से हाँ है, लेकिन कुछ बारीकियों के साथ।
</RoboAcademyText>

## डेटा प्रतिनिधित्व और परिवर्तन

शायद कच्चे डेटा को संसाधित करना और प्रस्तुत करना एआई सहायकों का सबसे अच्छा काम है। पिछले गाइड में, हमने एआई का उपयोग करके सफलतापूर्वक एक यूएमएल आरेख बनाया था, लेकिन सामान्य तौर पर, डेटा के किसी भी संरचित सरणी को कुछ आंकड़ों के साथ आसानी से एक आरेख या तालिका में बदला जा सकता है। उदाहरण के लिए, चैटजीपीटी को स्मार्ट होम से सफल डेटालॉग लेनदेन की संख्या की गणना करने और [सबस्कैन] (https://robonomics.subscan.io/) पर रोबोनॉमिक्स पैराचेन से कच्चे डेटा के आधार पर उन्हें घंटे के हिसाब से वितरित करने का काम सौंपा गया था। यहां परिणामी आउटपुट का एक हिस्सा है:

| Hour  | Successful Transactions | Total Transactions | Percentage of Success |
|-------|-------------------------|--------------------|-----------------------|
| 13:00 | 4                       | 4                  | 100%                  |
| 14:00 | 5                       | 5                  | 100%                  |
| 15:00 | 6                       | 6                  | 100%                  |
| 16:00 | 5                       | 5                  | 100%                  |
| 17:00 | 5                       | 5                  | 100%                  |
| 18:00 | 6                       | 6                  | 100%                  |

चैटजीपीटी ने न केवल प्रति घंटे लेनदेन की संख्या की गणना की, बल्कि उनका प्रतिशत भी निकाला।

## गहन विश्लेषण

लेकिन क्या होगा अगर हम एआई को असंरचित डेटा के आधार पर गहन विश्लेषण करने के लिए कहें? दुर्भाग्य से, यहाँ वे समस्याएँ शुरू होती हैं जिनका हम पहले ही सामना कर चुके हैं: संदर्भ सीमाएँ और मतिभ्रम। उदाहरण के तौर पर, पहले बनाए गए स्मार्ट होम के होम असिस्टेंट से लॉग फ़ाइलें ली गईं, और चैटजीपीटी के लिए निम्नलिखित अनुरोध तैयार किया गया:

<RoboAcademyDialog>

Based this logs of smart home system, write section called "Analysis of IoT Hub Logs" in 1000 words. Add precise statistics of occurrences of found events and recommendations for solution of found problems.

</RoboAcademyDialog>

लॉग कुछ इस तरह दिखते हैं (कुल मिलाकर लॉग की लगभग 500 पंक्तियाँ):

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
    2023-05-29 14:17:28.617 चेतावनी (SyncWorker_6) [custom_components.robonomics.ipfs] Not enough account balance to store the file in Crust Network
    2023-05-29 14:17:28.634 DEBUG (MainThread) [custom_components.robonomics.robonomics] Send datalog states request, another datalog: False
    2023-05-29 14:17:28.638 DEBUG (SyncWorker_0) [custom_components.robonomics.robonomics] Start creating rws datalog
    2023-05-29 14:17:55.573 DEBUG (SyncWorker_0) [custom_components.robonomics.robonomics] Datalog created with hash: 0x396f26a5e3fdaa89910e7f78491f90150d6f9e59e9c7e85f6b9d090ade235077
    2023-05-29 14:19:40.007 चेतावनी (MainThread) [custom_components.local_luftdaten.sensor] REST request error: Cannot connect to host 192.168.13.141:80 ssl:default [Connect call failed ('192.168.13.141', 80)]

</LessonCodeWrapper>

जवाब में, एआई उपकरण अक्सर मतिभ्रम करना शुरू कर देता है, जो स्पष्ट रूप से अलग, गैर-मौजूद डेटा का विश्लेषण पेश करता है:

<RoboAcademyDialog>

<ChatGPT/>

The logs revealed a significant number of connectivity issues encountered by the IoT devices. Out of a total of 10,000 recorded events, 1,200 (12%) were related to connectivity problems.

...

The analysis identified a notable number of unauthorized access attempts to the smart home system. Approximately 300 (3%) events were logged, indicating potential security breaches. These attempts could lead to unauthorized control or access to sensitive information within the smart home.

...

The logs revealed a lack of regular firmware updates for the IoT devices, with only 20 (0.2%) events indicating successful updates. This finding raises concerns regarding the security and performance of the devices.

</RoboAcademyDialog>

अन्य मामलों में, एआई ने संदर्भ खो दिया। उदाहरण के लिए, सबस्कैन लेनदेन लॉग के लिए निम्नलिखित अनुरोध किया गया था:

<RoboAcademyDialog>

Analyze the logs below and tell me what kind of Smart Home System analysis can be done on them. These are the transaction logs for the SUB_CONTROLLER address received from the Robonomics parachain, related to the subscription IoT.

</RoboAcademyDialog>

इस तथ्य के बावजूद कि एआई को विशेष रूप से स्नातक की थीसिस और स्मार्ट होम ऑनलाइन पाठ्यक्रम के पाठ के संदर्भ में फिर से फीड किया गया था, फिर भी इसने डेटा के साथ एक भ्रामक उत्तर उत्पन्न किया जो लॉग में मौजूद ही नहीं था:

<RoboAcademyDialog>

<ChatGPT/>

User Behavior Analysis:

Analyzing the logs provided insights into user behavior within the Smart Home System. By examining the transaction details, we observed the following user behavior patterns:
- Most Frequently Used Features: Lighting control was the most frequently used feature, accounting for 45% of total transactions. Temperature control followed closely with 30% of total transactions, while security system monitoring and appliance automation accounted for 15% and 10% respectively.
- Usage Patterns: Users tended to interact with the Smart Home System more frequently during weekdays compared to weekends. This suggests that the system is primarily utilized for regular daily activities, such as lighting and temperature control, rather than special occasions or leisure activities.

</RoboAcademyDialog>

कुल मिलाकर, परिणाम अनुभाग लिखने के लिए एआई सहायकों का उपयोग सफल से अधिक असफल माना जा सकता है। हाँ, AI डेटा प्रस्तुत करने और संसाधित करने में मदद कर सकता है, लेकिन संक्षेप में, यह क्लासिक डेटा विज्ञान टूल की तुलना में बहुत कम समय बचाता है। इसके अतिरिक्त, उपयोगकर्ताओं को दिए गए उत्तरों की सटीकता के बारे में लगातार चिंता करने और उन्हें दोबारा जांचने की आवश्यकता है।

<RoboAcademyText fWeight="500">
अब हम अपनी स्नातक थीसिस के अंतिम खंड - निष्कर्ष पर आगे बढ़ सकते हैं, जहां हम न केवल थीसिस लिखना समाप्त करेंगे, बल्कि इस उद्देश्य के लिए एआई के उपयोग पर समग्र निष्कर्ष भी निकालेंगे।
</RoboAcademyText>