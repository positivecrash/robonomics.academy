---
title: "组装智能家居面板"
lastUpdate: Thu May 18 2023 10:46:29 GMT+0400 (Samara Standard Time)
description: 您将学习如何组装智能家居面板！
metaOptions: [学习]
defaultName: Introduction to open source solution for private smart homes
---

<LessonImages imageClasses="mb" src="smart-home-intro/spring-school-2023-smart-stand-intro.gif" />

## 智能家居面板 

这个面板旨在用作中央控制设备，上面显示最常用的开关和数据。还可以连接对讲机，用作室内监视器。基本上，这只是一个运行Android操作系统的平板电脑。您只需要提供电源。我们认为这个面板应安装在您放置室内监视器的地方

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcbdAJqbwHAQ3NeyWQUwSoS4drDexa3AEs7HXuM1BrUT1', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-1.png" />


## 灯开关

智能灯开关看起来或多或少像普通开关，只是使用按钮而不是开关。按下按钮后，按钮会回到原位。常规开关和智能开关之间的连接没有区别：将中性线连接到N，电源线连接到L，闪电线连接到L1。组装开关后，为了通过ZigBee配对它，请按下按钮至少5秒钟。

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/Qmb138DiQWWBgowMj2fC9kmiGYh9WEeytteSkqumWCv2LB', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-2.png" />

在两个按钮开关（或更多）的情况下，唯一的区别是第二（第三，...）行的灯。 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZiStYZG4rmyNPXXmCXsVPm7witPpnNJMBzD8GtxedgPo', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-3.png" />

## 智能灯泡 

智能灯泡可能是尝试智能设备最简单的方式，甚至不需要成为电工。它们可以远程控制，可以改变亮度或颜色。您可以将它们与智能开关一起安装，也可以单独使用。使用这些设备可以根据您的心情或室外条件打开一整页的自动化！新的灯泡可以通过ZigBee连接。如果找不到一个，可以将其开关5次


<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbiMHLJqnDpr1Whzvo6Y7zE33cQPuTs7furbt3JW2uiek', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-4.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmTzK4dY168HVgLvVBsRxR4M4vda55XC7pFhpW5kRexujQ', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-5.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZFpvVUavKc1Za9SeXqikrfySsfFHuVrkdzgbVB8um7T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-6.png" />

## 智能插座 

通常我们需要时常打开和关闭一些“不智能”的设备。如果我们通过智能插座给这样的设备供电，我们可以根据我们的需求、时间表或条件来打开/关闭它。此外，这样的插座可以监控能耗，因此我们可以得知这个设备消耗了多少能量。连接非常简单，只需按下智能插座上的按钮5秒钟即可配对

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRtmKXSv7csHLbKVuZkoA5Eb2zyTkEAbUxLYT6Qt1yxZH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-7.png" />

## 锅炉开关 

锅炉开关作为专用设备存在的原因是它可以承受更大的负荷。通常锅炉消耗3千瓦时甚至更多，因此常规（甚至智能）开关在这种情况下不适用。锅炉开关设计用于在这些条件下工作。连接和配对方式与灯开关几乎相同

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZyRtXXRYCrAQe6s6ZFJLXtUrH7SZHJC1Bt61kTrRX54', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-8.png" />

## Wifi/Zigbee Thermostat

看起来像普通的恒温器，但具有无线控制的能力。有两种选项：直接将加热系统连接到恒温器或将它们分开。在后一种情况下，恒温器将告诉我们模式（加热、制冷、风扇等）和温度

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRjxo9EGUvQiMm84xvXCL6LfrQJYza71vmFsa9Zpy7qmz', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-9.png" />

## 窗帘开关

另一个专用开关，这次是用于窗帘。从技术角度来看，不一定非要使用这个开关，我们可以使用任何三按钮开关并将其连接到窗帘电机，但这个开关带有特殊图标。为了配对开关，长按中间按钮

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRpEpZbyNkzby8Sk22Ymz59DbAcnty1B1osWc2kZr5FZ7', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-10.png" />

## 智能阀门控制器

根据您拥有的阀门选择控制器。最明显的情况是将此控制器与水泄漏传感器结合使用。要配对设备，请按住按钮5秒

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcjZcJ6P8Q5yUfSRx8R2mR4A7r2fi5bLs5uoUr3EAXLZs', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-11.png" />

## 水泄漏传感器

一种非常简单的设备，当其两个接触点连接时发送信号。水导电，当传感器下面有水时，其接触点会短路。传感器使用电池，通常可持续1-2年。通过ZigBee配对传感器，长按其按钮一段时间 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbgetJK1E8qQMcnBVREutpy8tKfbesqaxXiebjzpoyrdV', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-12.png" />

## 红外控制器

把它想象成你的遥控电视控制器...但是智能的！它不仅限于与电视一起使用。如果您的空调有一个遥控器，可以用这个智能遥控器替换。为了配对它，长时间按下控制器背面的复位按钮。有许带有现成命令的库，例如[https://github.com/smartHomeHub/SmartIR](https://github.com/smartHomeHub/SmartIR)。您所要做的就是找到您的电视或空调的型号

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmVjj92fMLbA6QJ5QhnmiqBT1huD5b7xyfi3VadHFDYwtm', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-13.png" />

## 门/窗传感器

另一个使用电池工作的传感器，有助于构建简单的安全系统或将其连接到灯光和其他设备。通过ZigBee配对它，将针插入孔中并长时间按下

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZyb66dKEqk9iCVKhaBk5ZKASi7dXdFSg2CBXY1fwuu5J', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-14.png" />

## 运动传感器
与门/窗传感器相同，可用于各种场景。最明显的是控制灯光或在您离开时检测运动

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmUA7TLg12pkhkbdGH6fwNDasU1kiyLHBJSutA2YG71Mka', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-15.png" />


## 温度和湿度传感器

了解您所处环境的条件是很重要的，对吧？这个传感器将为您提供温度和湿度测量值。然后，您可以使用这些数据来打开/关闭空调或其他供暖/制冷系统。要配对传感器，背面有一个按钮 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmayYFowfJVwQBVxPUSvi5inedqKzhyRZXp8fBUUayJnqH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-16.png" />

## 安全摄像头

最后，看看家里发生了什么是很好的。一个好的自动化是将运动传感器与摄像头连接起来，这样当检测到运动时，您将获得一个持续10秒的视频 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmX8nnDCgTx2kuwfAGv6B4orkEg4w6phtJtxSp44HfdD9T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-17.png"  />


## 智能板 
查看结果[https://www.youtube.com/watch?v=B3er7bwtvkw](https://www.youtube.com/watch?v=B3er7bwtvkw )
并自己玩[https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20](https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20)

