---
title: "Robonomics School 2024 / Cyprus Relocant Manual: 智能家居"
lastUpdate: 
description: "Cyprus Relocant Manual: 智能家居"
metaOptions: [学习, "Robonomics School 2024 / Cyprus Relocant Manual: 智能家居"]
defaultName: "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"
---

<LessonImages imageClasses="mb"  src='school-2024-cyprus-relocant-manual/Setup_SmartHome-Academy.jpg' alt="Cyprus Relocant Manual Cover" />

改变居住国家总是带来新的机遇，也带来挑战。在我的情况下，新的国家是塞浦路斯，我来这里建立公司。在搬迁前的最后10年，我住在一个大城市，那里有市政中央供暖、热水供应和廉价电力等一些特定的好处。在塞浦路斯，每栋房子和每间公寓在生活支持方面更加自治，但保持舒适生活的担忧落在业主身上。以热水为例。在寒冷的月份，你必须自己打开锅炉加热。公寓也需要自己加热。冬天我们打开/关闭电热毯和锅炉，夏天打开空调和驱蚊器。这不仅需要时间和精力，还需要金钱。

我在塞浦路斯的第一个冬天导致了天价的电费账单。这对我的预算是一个严重打击。一个可能的解决方案：改变习惯，适应新的条件。但搬迁后，你已经有足够多的烦恼了。作为一名工程师，我开始寻找能帮助我控制成本并让我的生活更舒适的解决方案，并且我想与你分享我的经验。

## 硬件选择

我想要开始的第一件事是选择一个生态系统。有线系统立即被排除在外，因为它们需要大量的预算和对公寓/房屋基础设施的严重干预。在无线设备中，有许多Sonoff和Tyua品牌的设备，但它们都通过互联网工作，在岛上并不总是可靠。更不用说在其他公司服务器上的个人数据的隐私和安全问题。我建议使用[Home Assistant](https://www.home-assistant.io)作为主要家庭服务器构建您的智能家居。优点：可以在没有外部互联网访问的情况下工作；可以在搬家时带走并在新地方部署而不会丢失设置；支持大量设备，包括智能电视、吸尘器等等。

用于设备无线连接的最流行的协议是Wi-Fi、Zigbee、蓝牙。在一个公寓中，这三种连接类型可能同时存在，但对于将普通设备变成智能设备的设备来说，使用Zigbee协议更加方便。在这种情况下，我们不需要担心它们的地址和覆盖范围，而且它们可以使用电池。Wi-Fi设备需要持续的电源连接，并且依赖于Wi-Fi信号的强度。即使在一个小公寓中，在路由器和卧室之间有几堵墙的情况下，有时也必须安装Wi-Fi Extender。在Zigbee的情况下，设备本身充当中继器。

回到塞浦路斯，我所需的最低设备数量如下：

## 计算机 - ���庭服务器

服务器的终极任务是为由Home Assistant控制的智能家居提供服务。最简单的方法是使用已经预配置的[Home Assistant Green](https://www.home-assistant.io/green/)。成本为[€70不含税](https://thepihut.com/products/home-assistant-green)。

<LessonImages src="school-2024-cyprus-relocant-manual/home-assistant-green.png" alt="Home Assistant green"/>

这个选项稍微复杂一些，但你甚至可以控制操作系统，这就是找/购买[Raspberry Pi](https://www.raspberrypi.com)。成本为[€90不含税](https://https://thepihut.com/products/raspberry-pi-5-starter-kit)。[安装](https://www.home-assistant.io/installation/)页面有许多选项适合所有口味。

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/raspberry-pi.png" alt="Raspberry Pi"/>

作为Zigbee协调器，我们选择[Sonoff Zigbee Dongle P或E](https://sonoff.tech/product/gateway-and-sensors/sonoff-zigbee-3-0-usb-dongle-plus-p/)，它们几乎总是在岛上可用。成本约为[€35](https://www.amazon.de/-/en/dp/B09KXTCMSC/)。您还可以从[此列表](https://www.zigbee2mqtt.io/guide/adapters/)中选择一个棒。

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/sonoff-zigbee-stick.png" alt="Sonoff Zigbee USB Stick"/>

我强烈建议为您的家庭服务器分配一个静态本地IP地址。如果无法进入路由器设置，则可以额外安装第二个路由器（我有[MikroTik](https://mikrotik.com/product/hap_ax2)，约[€80](https://www.mstronics.com/c/337_1345_485/networking-devices-routers.html?filter_id=154)），并在其上配置互联网。总的来说，最好为所有智能Wi-Fi设备分配静态IP。这通常对Home Assistant集成正常工作很重要。

## 锅炉开关

锅炉消耗3-3.5千瓦时，普通的智能开关无法使用。在选择时，请务必注意允许的电流；它应至少为16A，最好为20A。在岛上很难快速找到Zigbee开关，我从[中国](https://vi.aliexpress.com/item/1005006833309900.html)订购，大约花费20欧元。

<robo-academy-grid :columns="2" textAlign="center">
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-dimension.png" alt="Boiler Switch"/>
    </robo-academy-grid-element>
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-wiring.png" alt="Boiler Switch Wiring"/>
    </robo-academy-grid-element/>
</robo-academy-grid>

第一个也是最重要的自动化是在任何激活后N分钟关闭按钮。我们设置好后就不再考虑是否忘记关闭按钮或者它已经连续工作了第三天。一个Home Assistant的自动化示例，您需要用您的`device_id`和`entity_id`替换它：

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

您可以根据一年中的时间更改时间。例如，我需要在二月加热水一个小时，在四月30分钟就足够了。有用的是在水加热时向您的手机发送通知。

<robo-academy-note type="note" title="Homework">
  進行自動化操作，在指定的 X 分鐘後關閉鍋爐。要將時間設定為變量，請查看<a href="https://www.home-assistant.io/integrations/input_number/">此整合</a>
</robo-academy-note>

## 空调和电视的红外遥控器

遥控器带有Wi-Fi连接（需要持续电源）和Zigbee连接（电池操作）。

我尝试过的Wi-Fi选项来自制造商[Broadlink](https://www.ibroadlink.com/productinfo/762674.html)，在[Amazon](https://www.amazon.de/-/en/dp/B07ZSG9Y67/)购买，大约30欧元。初始设置时，您需要在手机上安装他们的应用程序并创建一个帐户，但之后红外遥控器将在本地网络上工作，连接到HA是通过[集成](https://www.home-assistant.io/integrations/broadlink/)完成的。为了进一步定制遥控器以适应您的需求，我建议查看[SmartIR](https://github.com/smartHomeHub/SmartIR)存储库 - 这是一个为不同空调和电视准备的大型命令库。

<robo-academy-note type="note" title="提示">
  如果找不到您特定的空调型号，请尝试同一制造商的其他型号。命令可能是相同的，您将能够连接您的空调。
</robo-academy-note>

<LessonImages src="school-2024-cyprus-relocant-manual/broadlink-ir.png" alt="Broadlink IR Remote Control"/>

Broadlink IR Remote 的設定範例：

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

运行在Zigbee���的遥控器不需要与电源保持持续连接，而是使用电池。一方面，这是一个优点，因为您可以将设备放在房间中的任何方便位置。另一方面，电池需要根据需要更换。这类遥控器的设置过程也可能与Broadlink不同。如果无法使用SmartIR库，则需要为每个命令单独训练遥控器，并保存在Home Assistant配置中。

可编程遥控器非常容易安装和配置；它们不需要壁挂或连接到空调总线。但是，由于设备之间缺乏反馈，存在轻微限制。我们无法验证空调是否已打开并准确执行我们发送的命令。但是，我们可以快速完成操作，而不会损坏公寓。为了为遥控器提供更多信息，您可以安装任何Zigbee温度和湿度传感器，例如[这个](https://vi.aliexpress.com/item/1005005595631552.html)售价10欧元，并将读数链接到遥控器。这样我们就有了简单的反馈，有趣的场景数量也增加了。

## 能源计量器

有半侵入式的电力消耗计量器，如下图所示：

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/energy-meter.png" alt="Energy Meter"/>

它们必须通���将L和N连接到输入来供电。另一边，感应环连接到电表上，我们将其挂在一个相位或消耗线上进行测量。大多数房屋和公寓有3个相位，这意味着您需要安装3个这样的模块。我在[Amazon](https://www.amazon.de/gp/product/B0C37DJXVD/)上以60欧元购买了一个，每个相位一个。老房子可能只有一个相位。

## 结论

对我来说，智能家居不是奢侈，而是必需品。这是我想要放松并与家人共度时光的地方，而不是浪费精力解决日常问题。在我这种情况下，上述套件的成本约为500欧元，加上几个晚上。结果是无价的！