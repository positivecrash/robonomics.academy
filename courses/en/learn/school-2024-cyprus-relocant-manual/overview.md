---
title: "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"
lastUpdate: 
description: "Cyprus Relocant Manual: Smart Home"
metaOptions: [Learn, "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"]
defaultName: "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"
---

<LessonImages imageClasses="mb"  src='school-2024-cyprus-relocant-manual/Setup_SmartHome-Academy.jpg' alt="Cyprus Relocant Manual Cover" />

Changing your country of residence always brings not only new opportunities, but also challenges. It so happened that in my case, the new country was Cyprus, where I came to build a company. For the last 10 years before moving, I lived in a big city, where I get used to certain benefits in the form of central heating from the city, hot water supply, and cheap electricity. In Cyprus, each house and each apartment is much more autonomous in terms of life support, but concerns about maintaining a comfortable life fall on the owner. Take hot water, for example. In the cold months, you have to turn on the boiler yourself to heat it up. The apartment also needs to be heated by yourself. In winter we turn on/off the thermal blanket and boiler, and in summer the air conditioner and mosquito repellent. This requires not only time and energy, but also money.

My first winter in Cyprus resulted in astronomical electricity bills. This was a serious blow to my budget. One possible solution: change your habits and adapt to new conditions. But after moving, you will already have enough worries. As an engineer, I started looking for solutions that would help me control costs and make my life more comfortable, and I want to share my experience with you.

## Hardware Choosing

The first thing I want to start with is choosing an ecosystem. Wired systems are immediately eliminated, as they require large budgets and serious intervention in the infrastructure of the apartment/house. Of the wireless devices, there are a huge number of devices under the Sonoff and Tyua brands, but they all work via the Internet, which does not always work reliably on the island. This is not to mention the issue of privacy and safety of your personal data on other company’s servers. I recommend building your smart home with [Home Assistant](https://www.home-assistant.io) as a main home server. Pros: can work without access to the external Internet; it is possible to take it with you when moving and deploy it in a new place without losing the settings; supports a huge number of devices, including smart TVs, vacuum cleaners, and much more.

The most popular protocols for wireless connection of devices are Wi-Fi, Zigbee, Bluetooth. In one apartment, all three types of connections can be found at once, but as for devices that make smart things out of ordinary things, it is more convenient to work with the Zigbee protocol. In this case, we do not need to worry about their addresses and coverage area, plus they can be battery operated. Wi-Fi devices require a constant connection to power and are dependent on the strength of the Wi-Fi signal. Even in a small apartment, where there are a couple of walls between the router and your bedroom, sometimes you have to install a Wi-Fi Extender. In the case of Zigbee, the devices themselves act as repeaters.

Returning to Cyprus, my required minimum of devices turned out to be as follows:

## Computer - Home Server

The ultimate task for the server is to serve a smart home controlled by Home Assistant. The easiest way is to take the already preconfigured [Home Assistant Green](https://www.home-assistant.io/green/). Cost [€70 excluding tax](https://thepihut.com/products/home-assistant-green).

<LessonImages src="school-2024-cyprus-relocant-manual/home-assistant-green.png" alt="Home Assistant green"/>

The option is a little more advanced, but you can even have control over the operating system, this is to find/buy [Raspberry Pi](https://www.raspberrypi.com). Cost [€90 excluding tax](https://https://thepihut.com/products/raspberry-pi-5-starter-kit). The [Installation](https://www.home-assistant.io/installation/) page has many options to suit all tastes.

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/raspberry-pi.png" alt="Raspberry Pi"/>

As a Zigbee Coordinator we take [Sonoff Zigbee Dongle P or E](https://sonoff.tech/product/gateway-and-sensors/sonoff-zigbee-3-0-usb-dongle-plus-p/), they are practically always available on the island. Cost about [€35](https://www.amazon.de/-/en/dp/B09KXTCMSC/). You can also choose a stick from [this list](https://www.zigbee2mqtt.io/guide/adapters/).

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/sonoff-zigbee-stick.png" alt="Sonoff Zigbee USB Stick"/>

I highly recommend assigning a static local IP address for your home server. If it is not possible to get into the router settings, then you can additionally install a second router (I have [MikroTik](https://mikrotik.com/product/hap_ax2), approximately [€80](https://www.mstronics.com/c/337_1345_485/networking-devices-routers.html?filter_id=154)), and configure the Internet on it. And in general, it is better for all smart Wi-Fi devices to assign a static IP. This is often important for Home Assistant integrations to work properly.

## Boiler Switch

The boiler consumes 3-3.5 kWh and a regular smart switch will not work. When choosing, be sure to pay attention to the permissible current; it should be at least 16A, and preferably 20A. It’s difficult to quickly find a Zigbee switch on the island itself, I ordered from [China](https://vi.aliexpress.com/item/1005006833309900.html), it cost about €20.

<robo-academy-grid :columns="2" textAlign="center">
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-dimension.png" alt="Boiler Switch"/>
    </robo-academy-grid-element>
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-wiring.png" alt="Boiler Switch Wiring"/>
    </robo-academy-grid-element/>
</robo-academy-grid>

The first and most important automation is to turn off the button N minutes after any activation. We set it up and no longer think about whether you forgot to turn off the button or whether it has been working for the third day. An example of automation for Home Assistant, you need to replace it with your `device_id` and `entity_id`:

<LessonCodeWrapper language="yaml" noCopyIcon>
    alias: Boiler turn off after 30 min
    description: ""
    trigger:
    - platform: device
        type: turned_on
        device_id: a7ee4b26ec5b9e36d959f7b4b8490c42
        entity_id: 61230c7b5528330e3b60ee38c5fe1f12
        domain: switch
        for:
        hours: 0
        minutes: 30
        seconds: 0
    condition: []
    action:
    - type: turn_off
        device_id: a7ee4b26ec5b9e36d959f7b4b8490c42
        entity_id: 61230c7b5528330e3b60ee38c5fe1f12
        domain: switch
    mode: single
</LessonCodeWrapper>

You can change the time throughout the year. For example, in February I need to heat the water for an hour, and in April 30 minutes is enough. Something useful is to add sending a notification to your phone when the water is heated.

<robo-academy-note type="note" title="Homework">
  Make an automation that will turn off the boiler after a specified X minutes. To set time as a variable, look at <a href="https://www.home-assistant.io/integrations/input_number/">this integration</a>
</robo-academy-note>

## IR Remote Controls for Air Conditioners and TV

Remote controls come with Wi-Fi connection (require constant power) and Zigbee connection (battery operated).

The Wi-Fi option I tried was from the manufacturer [Broadlink](https://www.ibroadlink.com/productinfo/762674.html), bought on [Amazon](https://www.amazon.de/-/en/dp/B07ZSG9Y67/), about €30. For the initial setup, you will have to install their application on your phone and create an account, but after that the IR remote control will work on the local network, connecting to HA is done using [integration](https://www.home-assistant.io/integrations/broadlink/). To further customize the remote control to suit your needs, I recommend looking at the [SmartIR](https://github.com/smartHomeHub/SmartIR) repository - this is a large library of ready-made commands for different air conditioners and TVs.

<robo-academy-note type="note" title="Tip">
  If your specific A/C model is not found, try other models from the same manufacturer. The commands will probably be the same and you will be able to connect your A/C.
</robo-academy-note>

<LessonImages src="school-2024-cyprus-relocant-manual/broadlink-ir.png" alt="Broadlink IR Remote Control"/>

Example configuration for Broadlink IR Remote:

<LessonCodeWrapper language="yaml" noCopyIcon>
    climate:
    - platform: smartir
        name: Living Room AC
        unique_id: living_room_ac
        device_code: 1390
        controller_data: remote.living_room_ir_remote_control
        temperature_sensor: sensor.0xa4c138b6ad623598_temperature
        humidity_sensor: sensor.0xa4c138b6ad623598_humidity 
</LessonCodeWrapper>

Remote controls running on Zigbee do not require a constant connection to power, but run on batteries. On the one hand, this is a plus, because you can place the device in any convenient place in the room. On the other hand, the batteries will need to be changed as needed. The setup process for such remote controls may also differ from Broadlink. If you can’t use the SmartIR library, the remote control will need to be trained for each command separately and saved in the Home Assistant configuration.

Programmable remote controls are very easy to install and configure; they do not require wall mounting or connection to an air conditioner bus. However, there is a slight limitation due to the lack of feedback between devices. We cannot verify that the A/C has turned on and is executing exactly the command that we sent. However, we do it quickly and without damage to the apartment. To give a little more information to the remote control, you can install any Zigbee temperature and humidity sensor, for example [this one](https://vi.aliexpress.com/item/1005005595631552.html) for €10, and link the readings to the remote control. This way we have simple feedback, and the number of interesting scenarios increases.

## Energy Meter

There are semi-invasive meters for electricity consumption, such as the one in the image below:

<LessonImages src="school-2024-cyprus-relocant-manual/energy-meter.png" alt="Energy Meter"/>

They must be powered by applying L and N to the input. On the other side, an induction ring is connected to the meter, which we hang on a phase or consumption line for measurement. Most houses and apartments have 3 phases, which means you need to install 3 such modules. I bought it on [Amazon](https://www.amazon.de/gp/product/B0C37DJXVD/) for €60, one for each phase. Older homes may only have one phase.

## Conclusion

For me, a smart home is not a luxury, but a necessity. This is a place where I want to relax and spend time with my family, without wasting energy on solving everyday issues. The cost of the above kit in my case was about €500 and a couple of evenings. The result is invaluable!