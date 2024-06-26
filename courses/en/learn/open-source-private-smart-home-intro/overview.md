---
title: "Introduction to open source solution for private smart homes"
lastUpdate: Tue May 09 2023 13:56:49 GMT+0400 (Samara Standard Time)
description: You will learn how to integrate open source solutions with inexpensive smart devices to make your smart home privately oriented and not dependent on clouds in its work.
metaOptions: [Learn]
defaultName: Introduction to open source solution for private smart homes
---

<LessonImages src="smart-home-intro/open-source-private-smart-home-intro.png" imageClasses="mb full" />

<RoboAcademyText>
  Hi all! Today I want to bring you to a conversation about a smart home, when there is a need for it, what it consists of and what it can give.
</RoboAcademyText>

## Smart homes: Solving heating and hot water woes

In 2022, I moved to Cyprus and I had to quickly get used to the living conditions in a new place. After Russia, the difference in attitude towards the use of energy resources is especially sharply felt. For example, in Cyprus there is no central heating. And until December, you could not think about it. And then it turned out that the temperature of my bedroom is the same as the temperature outside the window. To be honest, it's uncomfortable to sleep at +10 С ... brrr!

## Power up your savings with smart home monitoring

Further, there is no central hot water supply either. There are boilers that are installed on the roof and are heated by the sun. But in winter the sun is not enough to heat the tank of water. The apartment has a switch that starts the heating element inside the tank. The first thing that is inconvenient is that you need to turn it on in advance. Half an hour to an hour before taking a shower. In the evening, this scenario is still acceptable, but in the morning you will never have hot water. Second, you can easily forget to turn it off. As a result - a burnt-out heating element and an electricity bill.

By the way, electricity is very expensive here, and you need to pay for it every 2 months. It is impossible, at the moment, to determine the main consumer. It would be nice to have statistics on the main electrical consumers, such as air conditioning, underfloor heating, lighting, etc. Having real-time data on power consumption on hand, you can at least start analyzing what it is spent on.

## Essential components of a smart home: switches, sensors, and smart meters

It turns out that the first candidates for smart devices are various switches and power consumption monitoring. Next, you will probably think about controlling the air conditioner and underfloor heating according to a schedule or according to temperature readings. This means that we will need temperature and humidity sensors, relays for controlling underfloor heating and IR remote controls for air conditioners. Every house also has windows, and the windows usually have curtains - it would be cool when going to bed so that the curtains fall automatically. Thus, switches, sensors and smart meters form the basis of a smart home. And then you can dream up based on specific needs.

## Choosing the right smart home solution: KNX vs. Sonoff vs. Xiaomi

What smart home and automation solutions are on the market? We can think of KNX, which today is one of the most common solutions for use in medium and large automation systems for homes, offices and commercial premises. It has been on the market for over twenty years and is now supported by many major electrical equipment manufacturers. However, to assemble a KNX solution, a lot of engineering work needs to be done. The main logic is assembled, as a rule, in a separate switchboard cabinet. If it was not originally provided, installation in an existing apartment may be difficult or impossible at all, without making appropriate changes to the layout. In addition, KNX-based solutions are quite expensive.

Another approach might be to buy devices from Chinese manufacturers such as Sonoff or Xiaomi. Their main advantage is the price, ease of installation and configuration. Anyone will be able to install most sensors and devices in their homes. Somewhere you may need an electrician, for example, to install smart switches, but they will take the place of the old ones and you will not have to make changes to the layout of the apartment. The manufacturer offers a single application for managing devices. However, you must always remember that your data is sent somewhere to the server, and all communication with devices is impossible without an Internet connection.


## DIY smart home: Building a home server for full control

And another approach to building a smart home is based on the second, i.e. using available devices from the same Chinese manufacturers, but additionally install a home server in your apartment / house to get rid of the clouds. This is the path we took in our smart home solution. In the following parts, I will talk in detail about the assembly of our demo stand and its capabilities.

<RoboAcademyText fWeight="500">
  That's all for now! In the next lesson, we will dive deeper into the practical side of building a smart home and show you how to assemble a Smart Home Board. Stay tuned and get ready to take your first step towards creating a fully functional and automated home.
</RoboAcademyText>