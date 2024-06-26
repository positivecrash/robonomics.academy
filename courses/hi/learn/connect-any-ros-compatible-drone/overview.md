---
title: ROS-संगत ड्रोन कनेक्ट करें
lastUpdate: Thu May 04 2023 12:52:55 GMT+0400 (Samara Standard Time)
description: रोबोनॉमिक्स पैराचैन नियंत्रण के तहत किसी भी ros संगत रोबोट कनेक्ट करें।
metaOptions: [सीखें]
defaultName: Connect ROS-compatible drone
---


## भाग 1. लेन-द्वारा लॉन्च

**इस लेख में हम दिखाएंगे कि रोबोनॉमिक्स उपकरणों की मदद से आप किसी भी ROS-संगत उपकरण को नियंत्रित कर सकते हैं। हम वेब पर एक यादृच्छिक ड्रोन सिमुलेशन पैकेज खोजेंगे और इसे रोबोनॉमिक्स के साथ चलाने के लिए समायोजित करेंगे।**
**आवश्यकताएं:**

<List>

<li>Ubuntu 18.04 LTS</li>

<li class="flex">

ROS मेलोडिक + Gazebo + RViz (स्थापना मैनुअल [यहाँ](http://wiki.ros.org/melodic/Installation))

</li>

<li class="flex">

Robonomics नोड (बाइनरी फ़ाइल) (नवीनतम रिलीज [यहाँ](https://github.com/airalab/robonomics/releases))

</li>

</List>

<br/>

इस डेमो के इस हिस्से को कोड करने की पूरी प्रक्रिया नीचे एक वीडियो में प्रस्तुत की गई है।

https://www.youtube.com/watch?v=fDpwhBasQ5o&feature=youtu.be

<br/>

## 1. एक सिमुलेशन खोजें
आओ वेब पर सर्फ करें। `ROS ड्रोन सिम्युलेटर` के लिए गूगल करें। पहला लिंक आमतौर पर आपको [http://wiki.ros.org/tum_simulator](http://wiki.ros.org/tum_simulator) पर `tum_simulator` पृष्ठ दिखाएगा


<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/tum_simulator.jpg" alt="tum_simulator"/>

यह काफी पुराना है, इसलिए हमें अपने सिस्टम के लिए एक फोर्क ढूंढना बेहतर है। `tum_simulator Ubuntu 18 Gazebo 9 fork` के लिए गूगल करें। पहला परिणाम एक GitHub [रेपो](https://github.com/tahsinkose/sjtu-drone) है जिसमें एक उपयुक्त पैकेज है। इसे डाउनलोड करें

<LessonCodeWrapper language="bash">
mkdir -p drone_simulator_ws/src
cd drone_simulator_ws/src
git clone https://github.com/tahsinkose/sjtu-drone
cd ..
catkin build
</LessonCodeWrapper>

`~/.bashrc` में स्रोत कमांड जोड़ना न भूलें:

<LessonCodeWrapper language="bash" codeClass="big-code">
echo "source /home/$USER/drone_simulator_ws/devel/setup.bash" >> ~/.bashrc
source "~/.bashrc"
</LessonCodeWrapper>

अब हम सिमुलेशन चला सकते हैं ताकि हम देख सकें कि हमें ड्रोन को पैराचैन नियंत्रण के तहत लेने के लिए क्या करना होगा।

<LessonCodeWrapper language="bash">
roslaunch sjtu_drone simple.launch
</LessonCodeWrapper>

## 2. ROS विषयों की जांच करें
जब सिमुलेशन चल रहा हो, एक नया टैब में निम्नलिखित कमांड चलाएं ताकि ड्रोन द्वारा उपयोग किए जाने वाले विषयों की सूची देख सकें:

<LessonCodeWrapper language="bash">
rostopic list
</LessonCodeWrapper>

हम `/cmd_vel`, `/drone/takeoff` और `/drone/land` पर एक नजर डालें:

<LessonCodeWrapper language="bash">
rostopic info /cmd_vel
rostopic info /drone/takeoff
rostopic info /drone/land
</LessonCodeWrapper>

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/topics_info.jpg" alt="topics_info"/>

जैसा कि देखा जा सकता है, `Twist` और `Empty` प्रकार के संदेश होने चाहिए, वे `std_msgs` और `geometry_msgs` के हिस्से हैं, हम नियंत्रक में इसका उपयोग करेंगे। कुछ समय के लिए सिमुलेशन बंद करें।

## 3. नियंत्रक पैकेज डाउनलोड करें
सार्वजनिक रूप से, साधारण ROS रोबोट नियंत्रक से मुख्य अंतर एक कोड ब्लॉक है, जो [Robonomics IO](https://wiki.robonomics.network/docs/rinterface/) का उपयोग करके नेटवर्क में सभी लेन-द्वारा की गई सभी लेन की जांच करता है। पैकेज स्वयं GitHub पर उपलब्ध है। इसे डाउनलोड करें और कार्यस्थल निर्माण करें:

<LessonCodeWrapper language="bash">
cd ~/drone_simulator_ws/src
git clone https://github.com/PaTara43/drone_simulator_controller
cd drone_simulator_controller/src
chmod +x *.py
cd ~/drone_simulator_ws/src
catkin build
</LessonCodeWrapper>

## 4. DAPP में खातों का प्रबंधन करें
क्योंकि हम परीक्षण कर रहे हैं, चलो एक स्थानीय रोबोनॉमिक्स नेटवर्क नोड रोबोनॉमिक्स बाइनरी फ़ाइल के साथ बनाएं:

<LessonCodeWrapper language="bash">
./robonomics --dev
</LessonCodeWrapper>

**महत्वपूर्ण!** अगले लॉन्च के पहले `db` नामक निर्देशिका को हटाना आवश्यक है।

<LessonCodeWrapper language="bash" codeClass="big-code">
rm -rf /home/$USER/.local/share/robonomics/chains/dev/db
</LessonCodeWrapper>

एक सफ लॉन्च के बाद [इस](https://wiki.robonomics.network/docs/create-account-in-dapp/) मैनुअल का पालन करके खाते बनाएं। **हर खाते के सीड और पता सहेजना न भूलें! आपको लेन-देन के लिए इन्हें आवश्यकता होगी**। इन पतों, सीड और पथ को रोबोनॉमिक्स बाइनरी फ़ाइल में `config.config` में जोड़ें `robonomics_ws/src/robonomics_sample_controller/src`। इन खातों में कुछ पैसे (इकाइयाँ) भेजें:

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/balances.jpg" alt="balances"/>

## 5. पैराचैन नियंत्रण के तहत ड्रोन को लॉन्च करना

अब तक केवल रोबोनॉमिक्स स्थानीय नोड चल रहा होना चाहिए। एक अलग टर्मिनल में ड्रोन सिमुलेशन लॉन्च करें:

<LessonCodeWrapper language="bash">
roslaunch sjtu_drone simple.launch
</LessonCodeWrapper>

स्क्रिप्ट चलाएं:

<LessonCodeWrapper language="bash" codeClass="big-code">
rosrun drone_simulator_controller drone_sample_controller.py
</LessonCodeWrapper>

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/launched_drone.jpg" alt="launched_drone"/>

अब आप एक लेन-देन भेजकर ड्रोन को उड़ने के लिए ट्रिगर करने के लिए एक लेन-देन भेज कते हैं। इसे करने के लिए, आपको रोबोनॉमिक्स आईओ `write` उप-कमांड का उपयोग करना चाहिए रोबोनॉमिक्स बाइनरी फ़ाइल का:

<LessonCodeWrapper language="bash" codeClass="big-code">
echo "ON" | ./robonomics io write launch -r [DRONE_ADDRESS] -s [EMPLOYER’S_KEY]
</LessonCodeWrapper>

जहां `<DRONE_ADDRESS>` और `<EMPLOYER’S_KEY>` पहले से ही सहेजे गए स्ट्रिंग्स के साथ बदल दिए गए हैं।
आपको लॉग `"Taking Off"` देखना चाहिए और ड्रोन उड़ना शुरू होना चाहिए:

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/flying.jpg" alt="flying"/>

यही तरीका है कि किसी भी ROS-संगत रोबोट को रोबोनॉमिक्स पैराचैन नियंत्रण द्वारा नियंत्रित किया जा सकता है।


##  भाग 2. ब्लॉकचेन में डेटा सहेजना

**इस भाग में हम रोबोनॉमिक्स उपकरणों का उपयोग करके एक ड्रोन को पैराचैन द्वारा नियंत्रित होने देंगे। इस बार हम आईपीएफएस में डेटा भेजने और श्रृंखला विकल्पों में हैश स्टोर करने को जोड़ेंगे। नीचे निर्देश और कोड स्निपेट्स हैं। आवश्यकताएं:**

<List>

<li>Ubuntu 18.04 LTS</li>

<li class="flex">

ROS मेलोडिक + Gazebo + RViz (स्थापना मैनुअल [यहाँ](http://wiki.ros.org/melodic/Installation))
</li>

<li class="flex">

आईपीएफएस 0.4.22 (यहाँ से डाउनलोड करें [यहाँ से](https://dist.ipfs.io/go-ipfs/v0.4.22/go-ipfs_v0.4.22_linux-386.tar.gz) और स्थापित करें)
</li>

<li class="flex">

Robonomics नोड (बाइनरी फ़ाइल) (नवीनतम रिलीज [यहाँ](https://github.com/airalab/robonomics/releases))
</li>

<li>पायथन डिपेंडेंसीज़:
<LessonCodeWrapper language="bash">
pip install cv_bridge ipfshttpclient
</LessonCodeWrapper>
</li>

</List>

इस डेमो के इस हिस्से को कोड करने की पूरी प्रक्रिया नीचे एक वीडियो में प्रस्तुत की गई है।

https://www.youtube.com/watch?v=dliLb6GHgpo&feature=youtu.be

<br/>

## 1. डिपेंडेंसीज़ जोड़ें
अगर हम एक सिमुलेशन लॉन्च करते हैं और विषय सूची पर नजर डालते हैं (भाग 1 देखें), तो हमें दिखाई देगा, कि एक विषय है जिसमें फ्रंट कैमरा डेटा है और `sensor_msgs/Image` मैसेज प्रकार का उपयोग किया जा रहा है:

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/front_camera.jpg" alt="front_camera"/>

चलो हर 1 सेकंड में एक तस्वीर लेने की कोशिश करें और उड़ान के बाद इन तस्वीरों को IPFS पर प्रकाशित करें। अगर आपने पहले ट्यूटोरियल को पूरा किया है, तो आपको कुछ और डाउनलोड करने की आवश्यकता नहीं है। यह `drone_sample_controller_pictures.py` स्क्रिप्ट है।

## 2. DAPP में खातों का प्रबंधन करें
पिछले ट्यूटोरियल में किया गया जैसा, रोबोनॉमिक्स बइनरी फ़ाइल के साथ स्थानीय रोबोनॉमिक्स नेटवर्क नोड बनाएं:
<LessonCodeWrapper language="bash">
./robonomics --dev
</LessonCodeWrapper>

**महत्वपूर्ण!** अगले लॉन्च के पहले `db` नामक निर्देशिका को हटाना आवश्यक है।

<LessonCodeWrapper language="bash" codeClass="big-code">
rm -rf /home/$USER/.local/share/robonomics/chains/dev/db
</LessonCodeWrapper>

एक सफ लॉन्च के बाद [इस](https://wiki.robonomics.network/docs/create-account-in-dapp/) मैनुअल का पालन करके खाते बनाएं। **हर खाते के सीड और पता सहेजना न भूलें! आपको लेन-देन के लिए इन्हें आवश्यकता होगी**। इन पतों, सीड और पथ को रोबोनॉमिक्स बाइनरी फ़ाइल में `config.config` में जोड़ें `robonomics_ws/src/robonomics_sample_controller/src`। इन खातों में कुछ पैसे (इकाइयाँ) भेजें:

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/balances.jpg" alt="balances"/>

## 3. लॉन्
अब तक केवल रोबोनॉमिक्स स्थानीय नोड चल रहा होना चाहिए। एक अलग टर्मिनल में ड्रोन सिमुलेशन लॉन्च करें:

<LessonCodeWrapper language="bash">
roslaunch sjtu_drone simple.launch
</LessonCodeWrapper>

एक और लॉन्च में ipfs डेमन चालू करें:
<LessonCodeWrapper language="bash">
ifps init # you only need to do this once
ipfs daemon
</LessonCodeWrapper>

स्क्रिप्ट चलाएं:
<LessonCodeWrapper language="bash" codeClass="big-code">
rosrun drone_simulator_controller drone_sample_controller_pictures.py
</LessonCodeWrapper>

अब आप एक लेनदेन भेज सकते हैं जो ड्रोन को उड़ान भरने और तस्वीरें लेने के लिए प्रेरित करता है। इसे करने के लिए, आपको robonomics बाइनरी फ़ाइल के Robonomics IO `write` उप-कमांड का उपयोग करना चाहिए:

<LessonCodeWrapper language="bash" codeClass="big-code">
echo "ON" | ./robonomics io write launch -r [DRONE_ADDRESS] -s [EMPLOYER’S_KEY]
</LessonCodeWrapper>

जहां `<DRONE_ADDRESS>` और `<EMPLOYER’S_KEY>` पहले से ही सहेजे गए स्ट्रिंग्स के साथ बदल दिए गए हैं।
आपको लॉग `"Taking Off"` देखना चाहिए और ड्रोन उड़ना शुरू करना चाहिए और तस्वीरें लेना चाहिए:

<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/flying_picturing.jpg" alt="flying_picturing"/>

बाद में, जब काम पूरा हो जाए, Robonomics पोर्टल पर जाएं `डेवलपर` -> `चेन स्थिति` और `DRONE` डेटालॉग जोड़ें `“+”` बटन का उपयोग करके चयनित `datalog` के रूप में राज्य क्वेरी। टेलीमेट्री का IPFS हैश ब्लॉकचेन में सहेजा गया है। डेटा देखने के लिए बस हैश कॉपी करें और से स्थानीय [गेटवे](https://gateway.ipfs.io/ipfs/QmeYYwD4y4DgVVdAzhT7wW5vrvmbKPQj8wcV2pAzjbj886/docs/getting-started/) पते `localhost:8080/ipfs/` में जोड़ें:


<LessonImages imageClasses="mb" src="connect-any-ros-compatible-drone/datalog.jpg" alt="Voila"/>