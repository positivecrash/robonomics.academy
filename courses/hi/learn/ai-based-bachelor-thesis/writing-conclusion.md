---
title: "लेखन: निष्कर्ष"
description: एआई-संचालित उपकरणों के साथ अपने स्नातक थीसिस को शीघ्र प्रारंभ करें
metaOptions: [सीखें, एआई-संचालित उपकरणों के साथ अपने स्नातक थीसिस को शीघ्र प्रारंभ करें]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
हम स्नातक थीसिस के अंतिम भाग में पहुँच गए हैं। अब निष्कर्ष लिखने और इस शैक्षणिक कार्य के लिए एआई उपकरणों के अनुप्रयोग पर अपने छोटे से शोध का सारांश देने का समय आ गया है। अंततः, क्या यह अनुभव सफल रहा? और आधुनिक एआई सहायकों में अभी भी क्या कमी है?
</RoboAcademyText>

## थीसिस का निष्कर्ष

बुनियादी रूप से, हम पहले से ही जानते हैं कि एआई कैसे सामग्री को संक्षेपित करने में मदद कर सकता है, बस आवश्यक अनुरोध को तैयार करके। एकमात्र समस्या यह है कि पूरे स्रोत पाठ को उसे प्रदान करना है। जब तक लंबी पीडीएफ फ़ाइलों के लिए उचित समर्थन नहीं है, हम स्रोत पाठ को टुकड़ों में विभाजित करेंगे, प्रत्येक के लिए संक्षेप बनाने के लिए कहेंगे, और फिर टुकड़े को साथ भेजेंगे:

<RoboAcademyDialog>

Give me a summary for the following text in 500 words. 
</RoboAcademyDialog>

उत्सुकता के साथ, हमें यह पूछने का दृष्टिकोण बनाए रखें कि अंतिम पाठ को लेटेक्स में उपयोग के लिए स्वरूपित किया जाए, सिर्फ इस टास्क को हाथ में कैसे लिया जाएगा, यह देखने के लिए:

<RoboAcademyDialog>

Write a Conclusions section from the text below in 1000 words. Be sure to add summary of the thesis's contributions and main findings, implications and significance of the results for the smart home industry and related fields, recommendations for future research and development.

Take the resulting text and design it for LaTeX.
</RoboAcademyDialog>

परिणाम:

<LessonCodeWrapper language="uml" noCopyIcon noLines codeClass="big-code">
    \documentclass{article}
    \usepackage{lipsum}
    \begin{document}
    \section*{Conclusion}
    This bachelor's thesis aimed to design a secure and private 
    smart home system using Web3 technologies, specifically leveraging 
    blockchain and decentralized technologies.
    ...
    \end{document}

</LessonCodeWrapper>

अब हम अंतिम रूप से हमारी थीसिस को पूरा कर सकते हैं, सामान्य तरीके से एक अभिलेख बनाकर:

<RoboAcademyDialog>

Make an abstract for the bachelor's thesis based on this text in 100 words.
</RoboAcademyDialog>

## मार्गदर्शन का निष्कर्ष

सिद्धांत में, हमारा कार्य पूरा हो गया है। अगले, हम विभिन्न उपकरणों का उपयोग करके पाठ को प्रसंस्कृत करने का प्रयास कर सकते हैं, शब्दों को सुधारकर या कुछ अनुच्छेदों को विस्तारित करके। आप निम्नलिखित लिंक पर परिणाम से बनाया गया पीडीएफ फ़ाइल पा सकते हैं:

[https://cloudflare-ipfs.com/ipfs/Qme6rzPwiDGLLkUmWVLrCqgGMjcbqitYNcndznjNPb21E8](https://cloudflare-ipfs.com/ipfs/Qme6rzPwiDGLLkUmWVLrCqgGMjcbqitYNcndznjNPb21E8)

वर्तमान स्थिति में एआई उपकरणों की अनुप्रयोगिता के बारे में हम क्या निष्कर्ष निकाल सकते हैं? चलो पहले देखते हैं कि इसमें कुछ लाभ हैं:

1. एआई एक सामान्यीकृत कार्य वक्तव्य को संभाल सकता है। एक योजना बनाना, प्रकाशन खंडों का ढांचा तय करना, काम की दिशाएँ सुझाना - ये सभी बातें बहुत मदद कर सकती हैं जब शुरू कहाँ से करें या विचारों की कमी हो। इस दृष्टि में, एक एआई सहायक मुख्य ध्यान में विचारों की पेशकश करने वाला एक "बैकअप ब्रेन" हो सकता है।
2. एआई जनरल कंटेंट तैयार करने में अच्छा है। उन लोगों के लिए जो पाठ के मुख्य भाग को अच्छी तरह से तैयार कर सकते हैं, लेकिन "फुफ्फ" जोड़ने में संघर्ष करते हैं ताकि आवश्यक आकार तक पहुँचे, यह एक उत्कृष्ट समर्थन हो सकता है।
3. कुछ संवेदनाओं के साथ, एआई तेजी से पाठ का विश्लेषण कर सकता है और प्रमुख विचारों का सारांश प्रदान कर सकता है। हालांकि, अब तक कुछ सीमाओं के साथ काम करना है क्योंकि एआई सहायकों के डेवलपर्स अपनी प्रतिस्थिति को याद रखने की क्षमता को सुधारने पर काम कर रहे हैं।
4. यह अद्भुत है कि एआई अब डेटासेट का विश्लेषण करने और मौखिक विवरणों के आधार पर कार्यक्रम कोड लिखने का प्रयास कर सकता है। हालांकि, नतीजों में बहुत सावधानी बरतना महत्वपूर्ण है।
5. और बेशक, एक उन्नत खोज उपकरण के रूप में, एआई सहायक नियमित खोज इंजनों को पीछे छोड़ देता है।

हालांकि, निर्धारित किए गए विपरीत:

1. एआई एक सामान्यीकृत कार्य वक्तव्य को संभाल सकता है। योजना बनाना, प्रकाशन खंडों का ढांचा तय करना, काम की दिशाएँ सुझाना - ये सभी बातें बहुत मदद कर सकती हैं जब शुरू कहाँ से करें या विचारों की कमी हो। इस दृष्टि में, एक एआई सहायक मुख्य ध्यान में विचारों की पेशकश करने वाला एक "बैकअप ब्रेन" हो सकता है।
2. अधिक गहराई वाले जवाब प्राप्त करने में कठिनाई। एआई उपकरणों की यह "आलस्य" उपयोगकर्ता को उसे बेहतर करने के लिए अधिक और अधिक कल्पनाशील अनुरोधों के साथ संघर्ष करती है, जो ऐसा करने के लिए बेहतर होगा। यह एक कॉमिकल स्थिति में परिणत हो जाता है, जो वरिष्ठ कर्मचारी और इंटर्न के बीच संबंध की तुलना करता है: आखिरकार, पूर्ववर्ती के लिए अपने काम को स्वयं करना इसे करने से आसान होता है नाकि इंटर्न को कोशिश करने की। यह फिर से गति और सुविधा के लाभों को निलंबित कर देता है।

3. प्राप्त परिणाम की गुणवत्ता में अस्थिरता। एआई अक्सर एक ही क्वेरी के लिए विभिन्न सत्रों में पूरी तरह से भिन्न परिणाम प्रदान करता है, जो मूल रूप से उपयोगकर्ता को जीत की आशा में स्लॉट मशीन घुमाने पर मजबूर करता है। साथ ही, आप कभी यह सुनिश्चित नहीं हो सकते कि प्राप्त प्रतिक्रिया सर्वश्रेष्ठ और संभव है।

4. एआई उपकरण डेवलपर्स को शिकायत: मौजूदा उपकरणों का अनुभव बुरा है जो बड़े पाठ और डेटा के साथ उचित काम नहीं करने देता।

<RoboAcademyDialog>
“As a result, it can be said that AI tools can already be a good addition to manual, monotonous work in creating academic materials, but they still have many problems and shortcomings that prevent them from fully replacing human labor. In the future, these problems may be solved, and AI assistants will be able to significantly speed up and improve the process of creating scientific materials.”
</RoboAcademyDialog>

*(ऊपर का परिणाम नोशन एआई द्वारा उत्पन्न किया गया था)*