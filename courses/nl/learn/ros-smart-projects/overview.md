---
title: ROS-gebaseerde projecten voor slimme ruimtes
lastUpdate: Thu May 04 2023 12:53:19 GMT+0400 (Samara Standard Time)
description: ROS-gebaseerde projecten voor slimme ruimtes
metaOptions: [Leren]
defaultName: ROS-based projects for smart spaces
---

Gedurende zijn 15 jaar ontwikkeling werd het Robot Operating System-framework geïntegreerd met tientallen [verschillende robotapparaten](https://robots.ros.org/), en er zijn zelfs nog meer pakketten met algoritmes en tools ontwikkeld door de gemeenschap. Om eerlijk te zijn, er zijn nu zoveel projecten, en de chaos van de beschrijvingsstijl van hun repositories is zo gegroeid dat het momenteel behoorlijk problematisch is om projecten te vinden die zijn gewijd aan een specifiek onderwerp. 

Hier vind je een bescheiden lijst van ROS-gebaseerde projecten die zijn gewijd aan robots en IoT-apparaten die bedoeld zijn voor gebruik in een thuis- of kantooromgeving. Dit onderwerp is een van de pijlers van het Robonomics-platform. Ons doel is om te proberen deze projecten op één lijn te brengen met Robonomics, zowel vanuit een technisch integratiepunt als vanuit het perspectief van een interessante toepassing van deze apparaten in een robot-economie. Voel je vrij om deze lijst te gebruiken in je zoektocht naar ideeën en inspiratie.

Je kunt enkele voorbeelden bekijken van ROS-projecten geïntegreerd met Robonomics in onze [Leersectie](/learn).

<! - Op dit moment (**april 2021**), is Robonomics gericht op ROS **Melodic** en **Noetic** versies. Oudere versies kunnen ook werken, maar er kan extra integratiewerk nodig zijn. In de toekomst zal ondersteuning voor ROS-versie 2 worden toegevoegd. ->

De belangrijkste bronnen om te zoeken naar ROS-repositories en pakketten zijn te vinden [hier](https://index.ros.org/).

## Simulatie

Voordat we onze aandacht uitsluitend op apparaten richten, is het de moeite waard om te onthouden dat voor een groot aantal ROS-projecten er een optie bestaat om ze te testen in een simulatie. De meest populaire tool voor het 3D-modelleren van verschillende robots onder ROS is de [Gazebo](http://gazebosim.org/) simulator en zijn afsplitsingsproject, [Ignition](https://index.ros.org/r/ros_ign/). Beide simulators maken het mogelijk om apparaten te modelleren in verschillende moeilijke binnen- en buitenomgevingen, het model en de omgeving zelf aan te passen, controlealgoritmen te testen en te debuggen voordat over te gaan naar het echte apparaat. Ook is dit een uitstekend hulpmiddel voor training en situaties waarin een echt apparaat ontbreekt.

Al met al is dit een van de beste opties om te proberen Robonomics te integreren met een ROS-apparaat zonder enige kosten. Een echt scenario zou slechts kleine codeaanpassingen vereisen. Voor Gazebo heeft Robonomics een gedetailleerde handleiding die bestaat uit twee delen die [instellingen](https://wiki.robonomics.network/docs/en/connect-any-ros-compatible-robot-under-robonomics-parachain-control-1/) en [integraties](https://wiki.robonomics.network/docs/en/connect-any-ros-compatible-robot-under-robonomics-parachain-control-2/) behandelen (met behulp van een drone als voorbeeld). De grootste uitdaging ligt in het vinden van een kant-en-klaar model (bijvoorbeeld [hier](https://github.com/osrf/gazebo_models)) voor Gazebo of het proberen om je eigen model te maken met behulp van de [SDFormat](http://sdformat.org/) ontwikkeld voor simulators. 

## Single-board computers en andere boards

Dergelijke boards fungeren als een basiscomponent voor het verbinden van andere apparaten met ROS, voornamelijk sensoren en opnameapparaten (audio, foto en videorecorders, camera's, temperatuur-, druk- en stofconcentratiesensoren.) omdat het concept van een slimme ruimte de creatie van een [digitale tweeling](https://gateway.pinata.cloud/ipfs/QmNNdLG3vuTsJtZtNByWaDTKRYPcBZSZcsJ1FY6rTYCixQ/Robonomics_keypoint_March_2021.pdf) van infrastructuurobjecten impliceert. Bovendien kunnen boards fungeren als het belangrijkste rekenapparaat en controller voor het construeren van een robotisch mobiel apparaat. Hieronder wordt een lijst gepresenteerd van boards die ROS ondersteunen:

| Name and link                                                                                         |                                    Description                                  | ROS version | Last update |
|:-----------------------------------------------------------------------------------------------------:|---------------------------------------------------------------------------------|:-----------:|:-----------:|
|  [Raspberry Pi](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Melodic%20on%20the%20Raspberry%20Pi)| single board computer; RaspPi versions 2, 3 and 4 are available                 |   melodic   |     2020    |
|    [Arduino](http://wiki.ros.org/rosserial_arduino)                                                   | single board computer                                                           |    noetic   |     2021    |
|    [Phidgets](http://wiki.ros.org/phidgets)                                                           | sets of boards, various sensors and devices: Ph sensor, LED, RFID, motor control|    noetic   |     2020    |
|   [Sense HAT](https://wiki.ros.org/sensehat_ros)                                                      | shield for RaspPi with a set of sensors and LED                                 |    noetic   |     2020    |
|     [Navio2](https://navio2.emlid.com/)                                                               | autopliot shield for RaspPi 2,3,4                                               |    noetic   |     2020    |
|     [OpenCR](http://wiki.ros.org/opencr)                                                              | robot controller                                                                |    noetic   |     2021    |

<br/>

## Slimme huishoudelijke apparaten en huishoudelijke robots

Hier worden ROS-apparaten gepresenteerd waarvan het oorspronkelijke gebruik was voor slimme huizen of kantoren. De lijst varieert sterk, van stofzuigers en robotassistentie tot thuissystemen voor controle.

| Name and link                                             | Description                                                 |          ROS version          | Last update |
|:---------------------------------------------------------:|-------------------------------------------------------------|:-----------------------------:|:-----------:|
|  [Care-O-bot 4](http://wiki.ros.org/care-o-bot)           | household robot-assistant; a simulation is available        |            melodic            |     2021    |
|     [Kobuki](http://wiki.ros.org/kobuki)                  | mobile platform with different use cases (e.g. a waiter)    |            melodic            |     2020    |
|    [QTrobot](http://wiki.ros.org/Robots/qtrobot)          | humanoid social robot                                       | kinetic (melodic can be used) |     2020    |
|      [Nao](http://wiki.ros.org/nao)                       | humanoid robot; a simulation is available                   |            Melodic            |     2020    |
|     [TIAGo](http://wiki.ros.org/Robots/TIAGo)             | service robot with a manipulator; a simulation is available |            kinetic            |     2020    |
|     [Roomba](https://github.com/AutonomyLab/create_robot) | robot vacuum cleaner                                        |            melodic            |     2020    |
|    [OpenHAB](http://wiki.ros.org/iot_bridge)              | home automation system                                      |            kinetic            |     2017    |
|     [Sesame](https://index.ros.org/p/sesame_ros/)         | smart lock                                                  |            melodic            |     2021    |

<br/>

## Mobiele platforms en manipulatoren

Allereerst staat ROS bekend om de ondersteuning van mobiele robotica, van drones tot industriële manipulatoren, waarvoor veel pakketten zijn gemaakt die gelijktijdige lokalisatie en mapping realiseren ([SLAM](http://wiki.ros.org/rtabmap_ros)), de directe en inverse taak van kinematica oplossen, [trajectplanning](https://moveit.ros.org/), enz. Mobiele robotica dringt geleidelijk door in het dagelijks leven, daarom is het zeker interessant om bestaande ROS-robots te testen in hun gebruik binnen een slimme ruimte. De algemene lijst van op ROS gebaseerde mobiele platforms is vrij groot, daarom hebben we hier gekozen voor diegenen die potentieel handig zijn om te gebruiken in een thuis- of kantoorruimte. 

| Name and link                                             | Description                                | ROS version | Last update |
|:---------------------------------------------------------:|--------------------------------------------|:-----------:|:-----------:|
|   [turtlebot](http://wiki.ros.org/turtlebot3)             | mobile platform tailored for ROS           |    noetic   |     2020    |
|    [GoPiGo3](http://wiki.ros.org/Robots/gopigo3)          | mobile robot based on RaspPi               |   melodic   |     2020    |
|    [LoCoBot](http://wiki.ros.org/locobot)                 | mobile manipulator                         |   kinetic   |     2020    |
|   [ROSbot 2.0](http://wiki.ros.org/Robots/ROSbot-2.0)     | mobile platform; a simulation is available |    noetic   |     2021    |
|     [VOLTA](http://wiki.ros.org/Robots/Volta)             | mobile platform; a simulation is available |   melodic   |     2021    |
|    [evarobot](http://wiki.ros.org/Robots/evarobot)        | mobile platform; a simulation is available |    noetic   |     2020    |
|    [Freight](http://wiki.ros.org/Robots/freight)          | mobile platform; a simulation is available |   melodic   |     2021    |
|      [PR2](http://wiki.ros.org/Robots/PR2)                | mobile platform; a simulation is available |   melodic   |     2021    |