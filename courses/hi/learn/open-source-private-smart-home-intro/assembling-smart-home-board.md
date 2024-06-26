---
title: "स्मार्ट होम बोर्ड को असेंबल करना"
lastUpdate: Thu May 18 2023 10:46:29 GMT+0400 (Samara Standard Time)
description: आप सीखेंगे कि स्मार्ट होम बोर्ड को कैसे असेम्बल करें!
metaOptions: [सीखें]
defaultName: Introduction to open source solution for private smart homes
---

<LessonImages imageClasses="mb" src="smart-home-intro/spring-school-2023-smart-stand-intro.gif" />

## स्मार्ट होम पैनल 

यह पैनल केंद्रीय नियंत्रण उपकरण के रूप में उपयोग के लिए है जिसमें सबसे अधिक उपयोग किए जाने वाले स्विच और डेटा प्रदर्शित होता है। इसके अलावा, एक इंटरकॉम कनेक्ट करना और इसे एक इंडोर मॉनिटर के रूप में उपयोग करना संभव है। मूल रूप से, हमारे मामले में यह बस एंड्रॉयड ओएस चला रहा टैबलेट है। आपको बस पावर प्रदान करना है। हमें लगता है कि यह पैनल उस स्थान पर स्थापित किया जाना चाहिए जहां आप एक इंडोर मॉनिटर रखेंगे

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcbdAJqbwHAQ3NeyWQUwSoS4drDexa3AEs7HXuM1BrUT1', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-1.png" />


## लाइट स्विच

्मार्ट लाइट स्विच आम स्विच की तरह दिखते हैं, केवल यहाँ बटन का उपयोग स्विच के बजाय किया जाता है। एक बटन दबाने के बाद अपनी स्थिति में वापस आता है। एक नियमित स्विच और एक स्मार्ट स्विच के बीच कनेक्शन में कोई अंतर नहीं है: N को न्यूट्रल तार से कनेक्ट करें, L को पावर तार से कनेक्ट करें और L1 को लाइटिंग लाइन से कनेक्ट करें। स्विच को असेम्बल करने के बाद ZigBee के माध्यम से इसे पेयर करने के लिए कम से कम 5 सेकंड के लिए बटन दबाएं।

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/Qmb138DiQWWBgowMj2fC9kmiGYh9WEeytteSkqumWCv2LB', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-2.png" />

दो बटन वाले स्विच (या अधिक) के मामले में, एकमात्र अंतर रोशनी की दूसरी (तीसरी,…) लाइन का है। 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZiStYZG4rmyNPXXmCXsVPm7witPpnNJMBzD8GtxedgPo', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-3.png" />

## स्मा्ट लाइट बल्ब 

स्मार्ट लाइट बल्ब शायद सबसे आसान तरीका है कुछ स्मार्ट को आजमाने का, आपको इलेक्ट्रीशियन होने की जरूरत भी नहीं है। इन्हें दूरस्थ से नियंत्रित किया जा सकता है और इसकी चमक या रंग बदल सकते हैं। आप इन्हें स्मार्ट स्विच के साथ या अलग-अलग भी इंस्टॉल कर सकते हैं। इस तरह के उपकरणों का उपयोग आपकी मूड या आउटडोर स्थितियों के आधार पर ऑटोमेशन का एक पूरा पृष्ठ खोल सकता है! नए लाइट बल्ब ZigBee के माध्यम से कनेक्ट करने के लिए तैयार हैं। यदि आपको एक नहीं मिलता है, तो इसे 5 बार चालू और बंद करें


<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbiMHLJqnDpr1Whzvo6Y7zE33cQPuTs7furbt3JW2uiek', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-4.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmTzK4dY168HVgLvVBsRxR4M4vda55XC7pFhpW5kRexujQ', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-5.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZFpvVUavKc1Za9SeXqikrfySsfFHuVrkdzgbVB8um7T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-6.png" />

## स्मार्ट सॉकेट 

हमें अक्सर कुछ “बुद्धिहीन” उपकरणों को चालू और बंद करने की आवश्यकता होती है। अगर हम ऐसे एक उपकरण को स्मार्ट सॉकेट के माध्यम से चालू करते हैं तो हम अपनी आवश्यकताओं, अनुसूचियों या स्थितियों के अनुसार इसे चालू / बंद कर सकते हैं। इसके अलावा ऐसे सॉकेट ऊर्जा की खपत को मॉनिटर कर सकते हैं ताकि हमें यह डेवाइस कितनी ऊर्जा खपत करता है का डेटा हो। कनेक्शन काफी आसान है, स्मार्ट सॉकेट को पेयर करने के लिए 5 सेकंड के लिए बटन दबाएं

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRtmKXSv7csHLbKVuZkoA5Eb2zyTkEAbUxLYT6Qt1yxZH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-7.png" />

## बॉयलर स्विच 

बॉयलर स्विच का अस्तित्व एक विशेष उपकरण के रूप में है क्योंकि इसमें अधिक भार सह सकता है। आम तौर पर बॉयल 3kWh या इससे भी अधिक खपत करते हैं, इसलिए नियमित (या स्मार्ट) स्विच इस स्थिति में उपयुक्त नहीं हैं। बॉयलर स्विच इन शर्तों के तहत काम करने के लिए डिज़ाइन किया गया है। कनेक्शन और पेयरिंग लाइट स्विच के लिए बहुत ही समान हैं

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZyRtXXRYCrAQe6s6ZFJLXtUrH7SZHJC1Bt61kTrRX54', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-8.png" />

## वाईफ़ाई / जिगबी थर्मोस्टैट

यह एक साधारण थर्मोस्टैट जैसा दिखता है लेकिन इसमें वायरलेस रूप से नियंत्रित किया जा सकता है। विकल्प हैं: थर्मोस्टैट को हीटिंग सिस्टम से सीधे कनेक्ट करें या उन्हें अलग करें। इसके बाद थर्मोस्टैट हमें मोड (हीट, कूल, फैन, आदि) और तापमान बताएगा

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRjxo9EGUvQiMm84xvXCL6LfrQJYza71vmFsa9Zpy7qmz', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-9.png" />

## पर्दे स्विच

एक और विशेष स्विच, इस बार पर्दों के लिए। तकनीकी दृष्टिकोण से इस स्विच का उपयोग करना आवश्यक नहीं है, हम किसी भी तीन बटन स्विच का उपयोग कर सकते हैं और इसे पर्दे के मोटर से जोड़ सकते हैं, लेकिन यह एक विशेष आइकन्स के साथ आता है। स्विच को पेयर करने के लिए म्य बटन पर लंबे समय तक दबाएं

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRpEpZbyNkzby8Sk22Ymz59DbAcnty1B1osWc2kZr5FZ7', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-10.png" />

## स्मार्ट वाल्व नियंत्रक

आपके पास जो वाल्व है उसके अनुसार एक नियंत्रक चुनें। सबसे स्पष्ट स्थिति यह है कि इस नियंत्रक को एक पानी के लीकेज सेंसर के साथ मिलाकर उपयोग करें। डिवाइस को पेयर करने के लिए बटन को 5 सेकंड के लिए दबाएं

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcjZcJ6P8Q5yUfSRx8R2mR4A7r2fi5bLs5uoUr3EAXLZs', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-11.png" />

## जल रसाव सेंसर

एक बहुत ही सरल उपकरण जो एक संकेत भेजता है जब इसके दो संपर्क जुड़े होते हैं। पानी विद्युत चालित करता है और जब सेंसर के नीचे पानी होता है तो इसके संपर्क शॉर्ट हो जाते हैं। सेंसर एक बैटरी पर काम करता है और आम तौर पर 1-2 साल तक चलता है। सेंसर को ZigBee के माध्यम से पेयर करने के लिए इसके बटन पर थोड़ी देर के लिए लॉन्ग प्रेस करें 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbgetJK1E8qQMcnBVREutpy8tKfbesqaxXiebjzpoyrdV', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-12.png" />

## आईआर कंट्रोलर

इसे अपने रिमोट टीवी कंट्रोलर के रूप में सोचें... लेकिन स्मार्ट वाला! और यह केवल टीवी के साथ काम करने के लिए सीमित नहीं है। अगर आपके ए/सी में एक रिमोट कंट्रोलर है, तो इसे इस स्मार्ट वाले से दला जा सकता है। इसे पेयर करने के लिए, कंट्रोलर के पीछे रीसेट बटन को थोड़ी देर के लिए दबाएं। तैयार उपयोग के लिए कमांड्स के साथ कई पुस्तकालय हैं, उदाहरण के लिए [https://github.com/smartHomeHub/SmartIR](https://github.com/smartHomeHub/SmartIR)। आपको बस अपने टीवी या ए/सी के मॉडल को खोजना है

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmVjj92fMLbA6QJ5QhnmiqBT1huD5b7xyfi3VadHFDYwtm', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-13.png" />

## दरवाजा/खिड़की सेंसर

एक और सेंसर जो एक बैटरी पर काम करता है लेकिन एक सरल सुरक्षा प्रणाली या लाइट्स और अन्य उपकरणों से जुड़ने में मदद करता है। ZigBee के माध्यम से इसे पेयर करने के लिए, होल में एक सुई डालें और थोड़ी देर के लिए दबाएं

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZyb66dKEqk9iCVKhaBk5ZKASi7dXdFSg2CBXY1fwuu5J', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-14.png" />

## मोशन सेंसर
दरवाजा/खिड़की सेंसर की तरह, इसे विभिन्न परिदृश्यों में उपयोग किया जा सकता है। सबसे स्पष्ट उदाहरण लाइट्स को नियंत्रित करना या जब आप दूर होते हैं तो गतियां पता करना हैं।

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmUA7TLg12pkhkbdGH6fwNDasU1kiyLHBJSutA2YG71Mka', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-15.png" />


## तापमान और नमी संवेदक

आपको जिन शर्तों में रहना है, उनको जानना अच्छा है, ना? यह संवेदक आपको तापमान और नमी की माप करने की सुविधा प्रदान करेगा। फिर आप इस डेटा का उपयोग करके अपने एसी को चालू / बंद या अन्य हीटिंग / कूलिंग सिस्टम को चालू कर सकते हैं। संवेदक को पेयर करने के लिए पीछे एक बटन है 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmayYFowfJVwQBVxPUSvi5inedqKzhyRZXp8fBUUayJnqH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-16.png" />

## सुरक्षा कैमरा

अंत में यह अच्छा है कि आप अपने घर में क्या हो रहा है, इसे देखना। एक अच्छा स्वचालन होगा कि आप मोशन संवेदक को कैमरा से कनेक्ट करें ताकि जब मोशन पता चले तो आपके पास 10 सेकंड की लंबी वीडियो हो। 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmX8nnDCgTx2kuwfAGv6B4orkEg4w6phtJtxSp44HfdD9T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-17.png"  />


## स्मार्ट बोर्ड 
परिणामों को देखें [https://www.youtube.com/watch?v=B3er7bwtvkw](https://www.youtube.com/watch?v=B3er7bwtvkw )
और खुद से इसके साथ खेलें [https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20](https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20)

