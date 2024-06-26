---
title: "Robonomics School 2024 / Manuel de relocalisation à Chypre : Maison intelligente"
lastUpdate: 
description: "Manuel de relocalisation à Chypre : Maison intelligente"
metaOptions: [Apprendre, "Robonomics School 2024 / Manuel de relocalisation à Chypre : Maison intelligente"]
defaultName: "Robonomics School 2024 / Cyprus Relocant Manual: Smart Home"
---

<LessonImages imageClasses="mb"  src='school-2024-cyprus-relocant-manual/Setup_SmartHome-Academy.jpg' alt="Cyprus Relocant Manual Cover" />

Changer de pays de résidence apporte toujours non seulement de nouvelles opportunités, mais aussi des défis. Il se trouve que dans mon cas, le nouveau pays était Chypre, où je suis venu pour construire une entreprise. Au cours des 10 dernières années avant de déménager, j'ai vécu dans une grande ville, où j'avais l'habitude de certains avantages sous forme de chauffage central de la ville, d'approvisionnement en eau chaude et d'électricité bon marché. À Chypre, chaque maison et chaque appartement sont beaucoup plus autonomes en termes de support de vie, mais les préoccupations concernant le maintien d'une vie confortable incombent au propriétaire. Prenez l'eau chaude, par exemple. Pendant les mois froids, vous devez allumer le chauffe-eau vous-même pour le chauffer. L'appartement doit également être chauffé par vous-même. En hiver, nous allumons/éteignons la couverture thermique et le chauffe-eau, et en été, le climatiseur et le répulsif contre les moustiques. Cela nécessite non seulement du temps et de l'énergie, mais aussi de l'argent.

Mon premier hiver à Chypre s'est soldé par des factures d'électricité astronomiques. Cela a été un sérieux coup pour mon budget. Une solution possible : changer vos habitudes et vous adapter aux nouvelles conditions. Mais après le déménagement, vous aurez déjà assez de soucis. En tant qu'ingénieur, j'ai commencé à chercher des solutions qui m'aideraient à contrôler les coûts et à rendre ma vie plus confortable, et je veux partager mon expérience avec vous.

## Choix du matériel

La première chose avec laquelle je veux commencer est le choix d'un écosystème. Les systèmes câblés sont immédiatement éliminés, car ils nécessitent des budgets importants et une intervention sérieuse dans l'infrastructure de l'appartement/maison. Parmi les appareils sans fil, il existe un grand nombre d'appareils des marques Sonoff et Tyua, mais ils fonctionnent tous via Internet, ce qui ne fonctionne pas toujours de manière fiable sur l'île. Sans parler de la question de la confidentialité et de la sécurité de vos données personnelles sur les serveurs d'autres entreprises. Je recommande de construire votre maison intelligente avec [Home Assistant](https://www.home-assistant.io) comme serveur domestique principal. Avantages : peut fonctionner sans accès à Internet externe ; il est possible de l'emporter avec vous lors d'un déménagement et de le déployer dans un nouvel endroit sans perdre les paramètres ; prend en charge un grand nombre d'appareils, y compris les téléviseurs intelligents, les aspirateurs, et bien plus encore.

Les protocoles les plus populaires pour la connexion sans fil des appareils sont le Wi-Fi, le Zigbee, le Bluetooth. Dans un appartement, les trois types de connexions peuvent être trouvés en même temps, mais en ce qui concerne les appareils qui transforment des choses ordinaires en choses intelligentes, il est plus pratique de travailler avec le protocole Zigbee. Dans ce cas, nous n'avons pas besoin de nous soucier de leurs adresses et de leur zone de couverture, en plus ils peuvent fonctionner sur batterie. Les appareils Wi-Fi nécessitent une connexion constante à l'alimentation et dépendent de la force du signal Wi-Fi. Même dans un petit appartement, où il y a quelques murs entre le routeur et votre chambre à coucher, parfois vous devez installer un répéteur Wi-Fi. Dans le cas du Zigbee, les appareils eux-mêmes agissent comme des répéteurs.

En revenant à Chypre, mon minimum requis de dispositifs s'est avéré être le suivant:

## Ordinateur - Serveur domestique

La tâche ultime du serveur est de servir une maison intelligente contrôlée par Home Assistant. Le moyen le plus simple est de prendre le [Home Assistant Green](https://www.home-assistant.io/green/) déjà préconfiguré. Coût [70 € hors taxes](https://thepihut.com/products/home-assistant-green).

<LessonImages src="school-2024-cyprus-relocant-manual/home-assistant-green.png" alt="Home Assistant green"/>

L'option est un peu plus avancée, mais vous pouvez même avoir le contrôle sur le système d'exploitation, il suffit de trouver/acheter un [Raspberry Pi](https://www.raspberrypi.com). Coût [90 € hors taxes](https://https://thepihut.com/products/raspberry-pi-5-starter-kit). La page [Installation](https://www.home-assistant.io/installation/) propose de nombreuses options pour tous les goûts.

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/raspberry-pi.png" alt="Raspberry Pi"/>

En tant que Coordinateur Zigbee, nous prenons le [Sonoff Zigbee Dongle P ou E](https://sonoff.tech/product/gateway-and-sensors/sonoff-zigbee-3-0-usb-dongle-plus-p/), ils sont pratiquement toujours disponibles sur l'île. Coût environ [35 €](https://www.amazon.de/-/en/dp/B09KXTCMSC/). Vous pouvez également choisir un stick dans [cette liste](https://www.zigbee2mqtt.io/guide/adapters/).

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/sonoff-zigbee-stick.png" alt="Sonoff Zigbee USB Stick"/>

Je recommande vivement d'attribuer une adresse IP locale statique à votre serveur domestique. Si vous ne pouvez pas accéder aux paramètres du routeur, vous pouvez également installer un deuxième routeur (j'ai un [MikroTik](https://mikrotik.com/product/hap_ax2), environ [80 €](https://www.mstronics.com/c/337_1345_485/networking-devices-routers.html?filter_id=154)), et configurer Internet dessus. Et en général, il est préférable d'attribuer une IP statique à tous les appareils Wi-Fi intelligents. C'est souvent important pour que les intégrations de Home Assistant fonctionnent correctement.

## Commutateur de chaudière

La chaudière consomme 3-3,5 kWh et un commutateur intelligent ordinaire ne fonctionnera pas. Lors du choix, veillez à prêter attention au courant admissible ; il doit être d'au moins 16A, et de préférence 20A. Il est difficile de trouver rapidement un commutateur Zigbee sur l'île elle-même, j'ai commandé depuis [Chine](https://vi.aliexpress.com/item/1005006833309900.html), cela a coûté environ 20 €.

<robo-academy-grid :columns="2" textAlign="center">
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-dimension.png" alt="Boiler Switch"/>
    </robo-academy-grid-element>
    <robo-academy-grid-element>
      <LessonImages src="school-2024-cyprus-relocant-manual/boiler-switch-wiring.png" alt="Boiler Switch Wiring"/>
    </robo-academy-grid-element/>
</robo-academy-grid>

La première et la plus importante automatisation consiste à éteindre le bouton N minutes après toute activation. Nous le configurons et ne pensons plus à savoir si vous avez oublié d'éteindre le bouton ou s'il fonctionne depuis le troisième jour. Un exemple d'automatisation pour Home Assistant, vous devez le remplacer par votre `device_id` et `entity_id` :

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

Vous pouvez changer l'heure tout au long de l'année. Par exemple, en février, j'ai besoin de chauffer l'eau pendant une heure, et en avril, 30 minutes suffisent. Il est utile d'ajouter l'envoi d'une notification sur votre téléphone lorsque l'eau est chauffée.

<robo-academy-note type="note" title="Homework">
  Réalisez un automatisme qui éteindra la chaudière après X minutes spécifiées. Pour définir l'heure comme variable, consultez <a href="https://www.home-assistant.io/integrations/input_number/">cette intégration</a>
</robo-academy-note>

## Télécommandes IR pour climatiseurs et téléviseurs

Les télécommandes sont livrées avec une connexion Wi-Fi (nécessitent une alimentation constante) et une connexion Zigbee (fonctionnent sur batterie).

L'option Wi-Fi que j'ai essayée était du fabricant [Broadlink](https://www.ibroadlink.com/productinfo/762674.html), achetée sur [Amazon](https://www.amazon.de/-/en/dp/B07ZSG9Y67/), environ 30 €. Pour la configuration initiale, vous devrez installer leur application sur votre téléphone et créer un compte, mais après cela, la télécommande IR fonctionnera sur le réseau local, la connexion à HA se fait en utilisant [l'intégration](https://www.home-assistant.io/integrations/broadlink/). Pour personnaliser davantage la télécommande pour répondre à vos besoins, je recommande de consulter le référentiel [SmartIR](https://github.com/smartHomeHub/SmartIR) - il s'agit d'une grande bibliothèque de commandes prêtes à l'emploi pour différents climatiseurs et téléviseurs.

<robo-academy-note type="note" title="Conseil">
  Si votre modèle de climatiseur spécifique n'est pas trouvé, essayez d'autres modèles du même fabricant. Les commandes seront probablement les mêmes et vous pourrez connecter votre climatiseur.
</robo-academy-note>

<LessonImages src="school-2024-cyprus-relocant-manual/broadlink-ir.png" alt="Broadlink IR Remote Control"/>

Exemple de configuration pour Broadlink IR Remote:

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

Les télécommandes fonctionnant sur Zigbee n'ont pas besoin d'une connexion constante à l'alimentation, mais fonctionnent sur des piles. D'une part, c'est un avantage, car vous pouvez placer l'appareil à n'importe quel endroit pratique dans la pièce. D'autre part, les piles devront être changées au besoin. Le processus de configuration de telles télécommandes peut également différer de Broadlink. Si vous ne pouvez pas utiliser la bibliothèque SmartIR, la télécommande devra être entraînée pour chaque commande séparément et enregistrée dans la configuration de Home Assistant.

Les télécommandes programmables sont très faciles à installer et à configurer; elles ne nécessitent pas de montage mural ni de connexion à un bus de climatisation. Cependant, il y a une légère limitation due au manque de retour d'information entre les appareils. Nous ne pouvons pas vérifier que la climatisation s'est allumée et exécute exactement la commande que nous avons envoyée. Cependant, nous le faisons rapidement et sans endommager l'appartement. Pour donner un peu plus d'informations à la télécommande, vous pouvez installer n'importe quel capteur de température et d'humidité Zigbee, par exemple [celui-ci](https://vi.aliexpress.com/item/1005005595631552.html) pour 10 €, et lier les lectures à la télécommande. De cette façon, nous avons un retour d'information simple, et le nombre de scénarios intéressants augmente.

## Compteur d'énergie

Il existe des compteurs semi-invasifs pour la consommation d'électricité, comme celui de l'image ci-dessous:

<LessonImages imageClasses="small" src="school-2024-cyprus-relocant-manual/energy-meter.png" alt="Energy Meter"/>

Ils doivent être alimentés en appliquant L et N à l'entrée. De l'autre côté, un anneau d'induction est connecté au compteur, que nous accrochons à une ligne de phase ou de consommation pour la mesure. La plupart des maisons et des appartements ont 3 phases, ce qui signifie que vous devez installer 3 de ces modules. Je l'ai acheté sur [Amazon](https://www.amazon.de/gp/product/B0C37DJXVD/) pour 60 €, un pour chaque phase. Les maisons plus anciennes peuvent n'avoir qu'une seule phase.

## Conclusion

Pour moi, une maison intelligente n'est pas un luxe, mais une nécessité. C'est un endroit où je veux me détendre et passer du temps avec ma famille, sans gaspiller d'énergie à résoudre des problèmes quotidiens. Le coût du kit ci-dessus dans mon cas était d'environ 500 € et quelques soirées. Le résultat est inestimable!