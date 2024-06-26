---
title: "Leçon n°2, Matériel de capteur"
description: 'MATÉRIEL DE CAPTEUR'
lessonNumber: 2
metaOptions: [Apprendre, Connectezezivité des capteurs et réseau de capteurs décentralisé]
defaultName: Sensors Connectivity & Decentralized Sensors Network
---

Si vous souhaitez participer à la surveillance de l'air avec le Réseau de Capteurs Décentralisés, vous devez obtenir une carte de pollution de l'air avec des capteurs. Il existe deux façons de le faire:

<List>

<li>commander toutes les pièces nécessaires et assembler la carte personnalisée vous-même.</li>
<li>commander une carte prête à l'emploi auprès de l'équipe Robonomics.</li>

</List>

## Assemblage manuel de la carte

Pour construire votre propre carte, vous devez trouver les composants suivants:

- Capteur laser PM2.5 et PM10 [SDS011](https://www.amazon.com/SDS011-Quality-Detection-Conditioning-Monitor/dp/B07FSDMRR5)

- Module sans fil série [NodeMcu V3 CH340](https://www.amazon.com/ACEIRMC-Wireless-Development-Compatible-MicroPython/dp/B092ZCG2X2) basé sur ESP8266

- Convertisseur mini560 DC-DC 5A [(exemple)](https://www.amazon.com/Alinan-Efficiency-Converter-Regulator-Stabilized/dp/B09W8P1QNM)

- Connecteur DC [(exemple)](https://www.amazon.com/CenryKay-DC-099-Threaded-Connector-Adapter/dp/B08CMMQMP6?th=1)

- Adaptateur secteur 12V/2А [(exemple)](https://www.amazon.com/TMEZON-Power-Adapter-Supply-2-1mm/dp/B00Q2E5IXW)

- boîtier de montage [(exemple)](https://www.amazon.com/LeMotech-Dustproof-Waterproof-Electrical-300mmx250mmx120mm/dp/B075DHT7X2/ref=sxin_18_ac_d_mf_brs?ac_md=7-4-TGVNb3RlY2g%3D-ac_d_mf_brs_brs&content-id=amzn1.sym.1ad31f34-ba12-4dca-be4b-f62f7f5bb10d%3Aamzn1.sym.1ad31f34-ba12-4dca-be4b-f62f7f5bb10d&crid=2ZDX87O7MINYG&cv_ct_cx=junction+box+plastic&keywords=junction+box+plastic&pd_rd_i=B075DHT7X2&pd_rd_r=2bbd50d4-9ef9-4fa1-a1a2-e55c482bce49&pd_rd_w=EcHLy&pd_rd_wg=z42mC&pf_rd_p=1ad31f34-ba12-4dca-be4b-f62f7f5bb10d&pf_rd_r=WDAX58YZKG6YKZ70X5QE&qid=1676642125&sprefix=Junction+Box%2Caps%2C451&sr=1-4-8b2f235a-dddf-4202-bbb9-592393927392)

De plus, vous pouvez installer des capteurs supplémentaires:

<List  type="numbers">

<li>

Avec interface I2C :

<List>

<li>

[BMP180](https://cdn-shop.adafruit.com/datasheets/BST-BMP180-DS000-09.pdf) — température et humidité

</li>

<li>

[BME/P280](https://www.mouser.com/datasheet/2/783/BST-BME280-DS002-1509607.pdf) — température, humidité, pression atmosphérique

</li>

<li>

[HTU21D](https://eu.mouser.com/ProductDetail/Measurement-Specialties/HTU21D?qs=tx5doIiTu8oixw1WN5Uy8A%3D%3D) — température et humidité

</li>

<li>

[CCS811 VOC SENSOR](https://www.sciosense.com/wp-content/uploads/documents/Application-Note-Baseline-Save-and-Restore-on-CCS811.pdf) — composés organiques volatils, équivalent CO2

</li>

</List>

</li>

<li>

Avec interface 1-Wire :

<List>

<li>

[DHT22(AM2302)](https://files.seeedstudio.com/wiki/Grove-Temperature_and_Humidity_Sensor_Pro/res/AM2302-EN.pdf) — température et humidité

</li>

<li>

[DS18B20](https://cdn.sparkfun.com/datasheets/Sensors/Temp/DS18B20.pdf) — température

</li>

</List>

</li>

</List>

Vous pouvez trouver le processus d'assemblage dans la vidéo ci-dessous. Il montre également le processus de flash, mais nous en parlerons plus tard.

<RoboAcademyYoutube link="https://www.youtube.com/watch?v=OdTd1sacCso" />

## Demander la carte Robonomics

Alternativement, vous pouvez demander la carte Robonomics. Pour ce faire, envoyez un e-mail à l'une des adresses suivantes :

- vm@multi-agent.io
- ping@airalab.org

La carte Robonomics est basée sur l'ESP8266 et est conçue pour une alimentation de 6 à 24V, en utilisant le convertisseur DC-DC DC MINI560. Cette carte vous permet de connecter le capteur de particules SDS011 et plusieurs capteurs supplémentaires (consultez la liste ci-dessus). Il existe également un modèle MINI plus petit avec une liste raccourcie de dispositifs connectables.

<LessonImages figure figureCaption="Full model of Robonomics board" src="sensors-connectivity-course/lesson-2-1.png" alt="Full model of Robonomics board"/>

<LessonImages  figure figureCaption="Mini model of Robonomics board" src="sensors-connectivity-course/lesson-2-2.png" alt="Mini model of Robonomics board"/>

Les schémas des deux modèles peuvent être trouvés ici : pour le [modèle complet](https://oshwlab.com/ludovich88/aira_sensor_rev0-1) et pour le [mini modèle](https://oshwlab.com/ludovich88/aira_sensor_d1_mini).

Jetons un coup d'œil plus attentif à la carte. Elle dispose de plusieurs ports de connexion (ils sont surlignés en bleu et vert).

<LessonImages imageClasses="mb" src="sensors-connectivity-course/lesson-2-3.png" alt="Full model of Robonomics board"/>

Bloc de bornes bleues, de gauche à droite (toutes les bornes sont signées) :

<List>
  <li class="flex">

  <code>12V</code> — borne pour connecter l'alimentation à la carte ; la tension recommandée est de 12 volts.

  </li>

  <li class="flex">

  <code>GND</code> de la terre (point de potentiel nul) — sert à la fois pour la connexion du potentiel nul de l'alimentation, et pour la connexion des capteurs.

  </li>

  <li class="flex">

  <code>POWER SENSOR</code> — sortie d'alimentation configurable à laquelle les capteurs sont connectés ; la sortie peut être réglée sur 3,3 ou 5 volts.

  </li>

  <li class="flex">

  <code>SDA</code> — ligne de données série, est utilisée pour connecter les capteurs via l'interface I2C.

  </li>

  <li class="flex">

  <code>SCL/1WIRE</code> — borne configurable à laquelle la ligne d'horloge série est connectée ; utilisée pour connecter les capteurs via l'interface I2C ou 1-Wire.

  </li>
</List>

Le réglage de la sortie d'alimentation pour le capteur et la sélection de l'interface se fait en réglant les cavaliers, marqués en jaune sur l'image (`5V`, `3V`, `I2C`, `1WIRE`). Les cavaliers sont installés horizontalement, les emplacements pour l'installation des cavaliers sont signés.


<RoboAcademyNote type="warning" title="WARNING">
Vous pouvez choisir la tension de l'alimentation en réglant un seul cavalier sur 3,3 volts ou 5 volts. Le réglage de deux cavaliers sur 3,3 et 5 volts endommagera le dispositif. La même règle s'applique lors du choix d'une interface pour les capteurs, installez un seul cavalier à la place de I2C ou 1-Wire. L'installation de deux cavaliers peut endommager le dispositif.
</RoboAcademyNote>

La carte dispose d'un bloc supplémentaire d'entrées, marqué en vert sur l'image (`GND`, `5V`, `SDA`, `SCL`).

Sur le côté gauche de la boîte bleue se trouve un interrupteur d'alimentation pour forcer la carte à redémarrer. Il est en position `ON` par défaut.

Après avoir configuré le capteur, il ne reste plus qu'à le flasher et le configurer.
