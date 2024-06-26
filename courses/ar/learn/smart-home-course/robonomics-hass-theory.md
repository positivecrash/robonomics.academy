---
title: "الدرس #1، الإحاطة النظرية"
lastUpdate: Thu May 04 2023 12:54:41 GMT+0400 (Samara Standard Time)
description: دورة مساعد المنزل
lessonNumber: 1
metaOptions: [تعلم، المنزل الذكي السيادي مع Robonomics و Home Assistant]
defaultName: Sovereign Smart Home with Robonomics and Home Assistant
---

## مفاتيح مكونات البيت الذكي السيادي 

<List>

1. **[Raspberry Pi](https://www.raspberrypi.org/), جهاز كمبيوتر لوحدة واحدة**.

يمكننا تحويل الجهاز إلى مركز IoT بعد تثبيت جميع البرامج اللازمة. الغرض الرئيسي من المركز هو تنظيم البروتوكولات والشبكات والتطبيقات والأجهزة المختلفة في المنزل الذكي.

2. **[Home Assistant](https://www.home-assistant.io/), برنامج نظام تحكم مفتوح المصدر**.

صمم ليكون مركزًا رئيسيًا للأجهزة الذكية. يمكنه فحص الشبكة تلقائيًا للأجهزة المعروفة ويسمح للمستخدمين بتكوين جميع الأتمتة اللازمة بسهولة. سنقوم بتثبيت Home Assistant على Raspberry Pi.

يتواصل Home Assistant مع الأجهزة ويخزن بياناتها محليًا، والتي للأسف لا تسمح لك بالتحكم في أجهزتك عن بُعد. لحل هذه المشكلة نستخدم شبكة Robonomics.

3. **[Robonomics Network](https://robonomics.network/), سحابة لامركزية للتحكم الآمن والموثوق في تطيقات IoT**.

تستخدم تقنيات web3، التي تدمج اللامركزية وتقنيات البلوكشين لحماية الأجهزة الذكية وبياناتها.

تم تنفيذ الوظائف الرئيسية لـ Robonomics استنادًا إلى بلوكشين (باراشين) من نظام Polkadot/Kusama. من بين الوظائف الرئيسية للباراشين القدرة على إرسال أمر لتشغيل الجهاز والقدرة على تخزين بيانات المستخدم على البلوكشين.

يحتوي باراشين Robonomics على ميزة اشتراك IoT التي تسمح للمستخدمين بإرسال معاملات إلى الباراشين، بدون رسوم، لمدة شهر واحد. في الجزء العملي من هذه الدورة، ستستخدم طريقة الاشتراك.

يتم تحقيق التفاعل بين مركز IoT وباراشين Robonomics باستخدام [robonomics-interface](https://github.com/Multi-Agent-io/Robonomics-interface) — مكتبة Python متخصصة في التفاعل مع Robonomics لبرمجة مريحة.

4. **[InterPlanetary File System](https://ipfs.tech/) (IPFS), برنامج نظام نداء نقطة لتخزين ومشاركة البيانات في نظام ملفات موزع**.

يُطلب IPFS من أجل تجنب تخزين الملفات الكبيرة على البلوكشين (لأنه سيكون مكلفًا للغاية)، بل يمكننا تخزين تجزئات IPFS للملفات، والتي تعمل كروابط لهذه الملفات.

## بروتوكولات الأجهزة الذكية
ستستخدم اثنين من البروتوكولات الرئيسية للأجهزة الذكية:

1. **[Zigbee](https://csa-iot.org/all-solutions/zigbee/), بروتوكول اتصال لاسلكي.**

يُستخدم على نطاق واسع لربط الأجهزة الذكية. تم تصميمه للاستهلاك المنخفض للطاقة، وسهولة الاستخدام ومرونة التكوين، ويدعم توبولوجية الشبكة الشبكية الذاتية التنظيم والتعافي الذاتي. هناك آلاف الأجهزة المتاحة في السوق مع دعم Zigbee، مما يجعله جذابًا لبناء حلول البيت الذكي. للتحكم في أجهزة Zigbee، تحتاج إلى بوابة تنقل البيانات بين شبكة Zigbee وشبكة أخرى (مثل Wi-Fi).

2. **[Message Queuing Telemetry Transport](https://mqtt.org/) (MQTT), بروتوكول نشر واشتراك مصمم للتحكم في تطبيقات الإنترنت الأشياء.**

البروتوكول خفيف الوزن، يتطلب موارد دنيا ويضمن موثوقية تسليم الرسائل. تم تصميم البروتوكول للشبكات ذات النطاق الترددي المنخفض، والتأخير العالي، وعدم الموثوقية، مما يجعله خيارًا ممتازًا لتشغيل حجم كبير من رسائل الاستشعار. يتطلب MQTT خادمًا يعمل كسمسار MQTT (في حالتنا سيعمل مع Raspberry Pi الخاص بنا). يستقبل السمسار جميع الرسائل من عملاء MQTT ثم يوجه الرسائل إلى العملاء المشتركين المناسبين.

## خيارات لاتصال Zigbee
ستكتشف سيناريوهين لربط الأجهزة بمساعد Home باستخدام Robonomics.

1. السيناريو الأول لا يستخدم بوابة Zigbee منفصلة لربط الأجهزة. بدلاً من ذلك، يتم استخدام مزيج من [محول Zigbee](https://www.zigbee2mqtt.io/guide/adapters/) وبرنامج [Zigbee2MQTT](https://www.zigbee2mqtt.io/guide/adapters/).

<LessonImages figure figureCaption="Architectural scheme of the scenario with Zigbee adapter" src="smart-house-course/lesson-1-1.png" alt="Architectural scheme of the scenario with Zigbee adapter"/>

يتصل المحول (مثل JetHome USB JetStick Z2) بـ Raspberry Pi ويعمل كواجهة بين الكمبيوتر واتصال الراديو Zigbee. Zigbee2MQTT هو برنامج يسمح بربط Zigbee بشبكات MQTT. يأخذ البرنامج الرسائل من شبكة Zigbee ويترجمها إلى رسائل سلة الاستخدام ومنظمة بشكل جيد من MQTT.

2. في السيناريو الثاني، يتم ربط الأجهزة باستخدام [SLS Gateway](https://github.com/slsys/Gateway) القائم على متحكم ESP32. لسهولة الاستخدام، قامت Robonomics بتطوير [تعديلنا الخاص](https://oshwlab.com/ludovich88/robonomics_sls_gateway_v01) للبوابة.

<LessonImages figure figureCaption="Architectural scheme of the scenario with SLS Gateway" src="smart-house-course/lesson-1-2.png" alt="Architectural scheme of the scenario with SLS Gateway"/>

يعمل SLS Gateway كمنسق لرسائل بروتوكول Zigbee ويسمح باستخدام معظم معدات Zigbee المتاحة. للتكامل مع مساعد Home، يتم استخدام بروتوكول MQTT.

## التحكم عن بعد

يتم تنفيذ التحكم عن بعد في البيت الذكي باستخدام [تطبيق Robonomics اللامركزي](https://dapp.robonomics.network/) (dapp)، الذي يوفر الوصول إلى وظائف الباراشين بطريقة سهلة للمستخدم. يتم ضمان أمان وعدم تغيير بيانات المستخدم من جهة واحدة من خلال إرسال البيانات المشفرة إلى IPFS (التي يمكن فك تشفيرها فقط بمفتاح المستخدم)، ومن جهة أخرى من خلال وضع هاش IPFS لهذه البيانات على البلوكشين.

</List>



