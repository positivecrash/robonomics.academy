---
title: "पाठ #2, सेंसर हार्डवेयर"
description: 'सेंसर हार्डवेयर'
lessonNumber: 2
metaOptions: [सीखना, सेंसर्स कनेक्टिविटी और डीसेंट्रलाइज्ड सेंसर्स नेटवर्क]
defaultName: Sensors Connectivity & Decentralized Sensors Network
---

यदि आप डिसेंट्रलाइज्ड सेंसर नेटवर्क के साथ हवा मॉनिटरिंग में भाग लेना चाहते हैं तो आपको सेंसर्स वाला एयर पोल्यूशन बोर्ड प्राप्त करना होगा। इसे करने के दो तरीके हैं:

<List>

<li>सभी आवश्यक भागों का ऑर्डर दें और अपने आप कस्टम बोर्ड को एसेम्बल करें।</li>
<li>Robonomics टीम से एक तैयार-उपयोग बोर्ड का ऑर्डर दें।</li>

</List>

## मैनुअल बोर्ड एसेम्बली

अपना खुद का बोर्ड बनाने के लिए, आपको निम्नलिखित कॉम्पोनेंट्स ढूंढने होंगे:

- लेजर PM2.5 और PM10 सेंसर [SDS011](https://www.amazon.com/SDS011-Quality-Detection-Conditioning-Monitor/dp/B07FSDMRR5)

- सीरियल वायरलेस मॉड्यूल [NodeMcu V3 CH340](https://www.amazon.com/ACEIRMC-Wireless-Development-Compatible-MicroPython/dp/B092ZCG2X2) ESP8266 पर आधारित

- 5A DC-DC mini560 कनवर्टर [(उदाहरण)](https://www.amazon.com/Alinan-Efficiency-Converter-Regulator-Stabilized/dp/B09W8P1QNM)

- DC कनेक्टर [(उदाहरण)](https://www.amazon.com/CenryKay-DC-099-Threaded-Connector-Adapter/dp/B08CMMQMP6?th=1)

- 12V/2А पावर एडाप्टर [(उदाहरण)](https://www.amazon.com/TMEZON-Power-Adapter-Supply-2-1mm/dp/B00Q2E5IXW)

- माउंटिंग बॉक्स [(उदाहरण)](https://www.amazon.com/LeMotech-Dustproof-Waterproof-Electrical-300mmx250mmx120mm/dp/B075DHT7X2/ref=sxin_18_ac_d_mf_brs?ac_md=7-4-TGVNb3RlY2g%3D-ac_d_mf_brs_brs&content-id=amzn1.sym.1ad31f34-ba12-4dca-be4b-f62f7f5bb10d%3Aamzn1.sym.1ad31f34-ba12-4dca-be4b-f62f7f5bb10d&crid=2ZDX87O7MINYG&cv_ct_cx=junction+box+plastic&keywords=junction+box+plastic&pd_rd_i=B075DHT7X2&pd_rd_r=2bbd50d4-9ef9-4fa1-a1a2-e55c482bce49&pd_rd_w=EcHLy&pd_rd_wg=z42mC&pf_rd_p=1ad31f34-ba12-4dca-be4b-f62f7f5bb10d&pf_rd_r=WDAX58YZKG6YKZ70X5QE&qid=1676642125&sprefix=Junction+Box%2Caps%2C451&sr=1-4-8b2f235a-dddf-4202-bbb9-592393927392)

आप अतरिक्त सेंसर भी इंस्टॉल कर सकते हैं:

<List  type="numbers">

<li>

I2C इंटरफेस के साथ:

<List>

<li>

[BMP180](https://cdn-shop.adafruit.com/datasheets/BST-BMP180-DS000-09.pdf) — तापमान और नमी

</li>

<li>

[BME/P280](https://www.mouser.com/datasheet/2/783/BST-BME280-DS002-1509607.pdf) — तापमान, नमी, वायुमंडलीय दबाव

</li>

<li>

[HTU21D](https://eu.mouser.com/ProductDetail/Measurement-Specialties/HTU21D?qs=tx5doIiTu8oixw1WN5Uy8A%3D%3D) — तापमान और नमी

</li>

<li>

[CCS811 VOC सेंसर](https://www.sciosense.com/wp-content/uploads/documents/Application-Note-Baseline-Save-and-Restore-on-CCS811.pdf) — वोलेटाइल आर्गेनिक कम्पाउंड्स, CO2 समकक्ष

</li>

</List>

</li>

<li>

1-वायर इंटरफेस के साथ:

<List>

<li>

[DHT22(AM2302)](https://files.seeedstudio.com/wiki/Grove-Temperature_and_Humidity_Sensor_Pro/res/AM2302-EN.pdf) — तापमान और नमी

</li>

<li>

[DS18B20](https://cdn.sparkfun.com/datasheets/Sensors/Temp/DS18B20.pdf) — तापमान

</li>

</List>

</li>

</List>

आप नीचे दिए गए वीडियो में असेम्बली प्रक्रिया पा सकते हैं। यह फ्लैशिंग प्रक्रिया भी िखाता है, लेकिन हम इसके बारे में बाद में बात करेंगे।

<RoboAcademyYoutube link="https://www.youtube.com/watch?v=OdTd1sacCso" />

## अनुरोध रोबोनॉमिक्स बोर्ड

वैकल्पिक रूप से, आप रोबोनॉमिक्स बोर्ड का अनुरोध कर सकते हैं। इसे करने के लिए, निम्नलिखित पतों में से किसी एक पर ईमेल भेजें:

- vm@multi-agent.io
- ping@airalab.org

रोबोनॉमिक्स बोर्ड ESP8266 पर आधारित है और 6-24V विद्युत आपूर्ति के लिए डिज़ाइन किया गया है, DC-DC कनवर्टर DC MINI560 का उपयोग करते हुए। यह बोर्ड आपको SDS011 कण संवेदक और कई अतिरिक्त संवेदकों (ऊपर सूची की जांच करें) से कनेक्ट करने की अनुमति देता है। एक और छोटा MINI मॉडल भी है जिसमें कनेक्ट किए जा सकने वाले उपकरणों की संक्षिप्त सूची है।

<LessonImages figure figureCaption="Full model of Robonomics board" src="sensors-connectivity-course/lesson-2-1.png" alt="Full model of Robonomics board"/>

<LessonImages  figure figureCaption="Mini model of Robonomics board" src="sensors-connectivity-course/lesson-2-2.png" alt="Mini model of Robonomics board"/>

दोनों मॉडलों के ब्लूप्रिंट यहाँ मिल सकते हैं: [पूर्ण मॉडल](https://oshwlab.com/ludovich88/aira_sensor_rev0-1) और [मिनी मॉडल](https://oshwlab.com/ludovich88/aira_sensor_d1_mini)।

चलो बोर्ड पर एक नजदीकी नज़र डालते हैं। इसमें कनेक्ट करने के लिए कई कनेक्टर पोर्ट हैं (वे नीले और हरे में हाइलाइट किए गए हैं)।

<LessonImages imageClasses="mb" src="sensors-connectivity-course/lesson-2-3.png" alt="Full model of Robonomics board"/>

ब्लू टर्मिनल ब्लॉक, बाएं से दाएं (सभी टर्मिनल साइन किए गए हैं):

<List>
  <li class="flex">

  <code>12V</code> — बोर्ड को विद्युत आपूर्ति से कनेक्ट करने के लिए टर्मिनल; सिफारिश की गई वोल्टेज 12 वोल्ट है।

  </li>

  <li class="flex">

  <code>GND</code> ज़मीन (शून्य संभावना का बिंदु) के लिए — विद्युत आपूर्ति की शून्य संभावना के कनेक्शन के लिए, और संवेदकों के कनेक्शन के लिए दोनों के लिए सेवा करता है।

  </li>

  <li class="flex">

  <code>POWER SENSOR</code> — सेट किए जाने वाले पावर आउटपुट जिसे संवेदक कनेक्ट कि जाते हैं; आउटपुट 3.3 या 5 वोल्ट पर सेट किया जा सकता है।

  </li>

  <li class="flex">

  <code>SDA</code> — सीरियल डेटा लाइन का उपयोग I2C इंटरफ़ेस के माध्यम से सेंसर को जोड़ने के लिए किया जाता है।

  </li>

  <li class="flex">

  <code>SCL/1WIRE</code> — सेट किए जाने वाला टर्मिनल जिसे सीरियल क्लॉक लाइन कनेक्ट किया जाता है; I2C या 1-वायर इंटरफेस के माध्यम से संवेदकों को कनेक्ट करने के लिए उपयोग किया जाता है।

  </li>
</List>

सेंसर के लिए शक्ति उत्पादन और इंटरफेस का चयन करने के लिए जंपर्स सेट करके किया जाता है, छवि में पीले रंग में चिह्नित (`5V`, `3V`, `I2C`, `1WIRE`). जंपर्स को क्षैतिज रूप से स्थापित किया जाता है, जंपर्स स्थापित करने के स्थानों के लिए चिह्नित है।


<RoboAcademyNote type="warning" title="चेतावनी">
आप शक्ति आपूर्ति के लिए वोल्टेज चुन सकते हैं केवल एक जंपर को 3.3 वोल्ट या 5 वोल्ट पर सेट करके। 3.3 और 5 वोल्ट पर दो जंपर सेट करने से उपकरण को क्षति पहुंच सकती है। सेंसर्स के लिए इंटरफेस चुनते समय भी यही नियम काम करता है, I2C या 1-Wire के स्थान पर केवल एक जंपर स्थापित करें। दो जंपर स्थापित करने से उपकरण को क्षति पहुंच सकती है।
</RoboAcademyNote>

बोर्ड में अतिरिक्त इनपुट ब्लॉक है, छवि में हरे रंग में चिह्नित (`GND`, `5V`, `SDA`, `SCL`).

नीले बॉक्स के बाएं ओर एक पावर स्विच है जिससे बोर्ड को रिबूट करने के लिए मजबूर किया जा सकता है। यह डिफ़ॉल्ट रूप से `ON` स्थिति में है।

सेंसर सेट करने के बाद, बस फ्लैश और कॉन्फ़िगर करना बचता है।
