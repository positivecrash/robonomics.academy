---
title: "Introductie tot open source oplossingen voor privé slimme huizen"
lastUpdate: Tue May 09 2023 13:56:49 GMT+0400 (Samara Standard Time)
description: Je leert hoe je open source oplossingen kunt integreren met goedkope slimme apparaten om je slimme huis privégericht te maken en niet afhankelijk van clouds in zijn werk.
metaOptions: [Leren]
defaultName: Introduction to open source solution for private smart homes
---

<LessonImages src="smart-home-intro/open-source-private-smart-home-intro.png" imageClasses="mb full" />

<RoboAcademyText>
  Hallo allemaal! Vandaag wil ik met jullie in gesprek gaan over een slim huis, wanneer er behoefte aan is, waaruit het bestaat en wat het kan bieden.
</RoboAcademyText>

## Slimme huizen: Het oplossen van verwarmings- en warmwaterproblemen

In 2022 verhuisde ik naar Cyprus en moest ik snel wennen aan de leefomstandigheden op een nieuwe plek. Na Rusland voel je het verschil in houding ten opzichte van het gebruik van energiebronnen extra scherp. Bijvoorbeeld, in Cyprus is er geen centrale verwarming. En tot december hoefde je daar niet aan te denken. En toen bleek dat de temperatuur in mijn slaapkamer hetzelfde is als de temperatuur buiten het raam. Eerlijk gezegd is het ongemakkelijk om te slapen bij +10 С ... brrr!

## Verhoog je besparingen met slimme huismonitoring

Verder is er ook geen centrale warmwatervoorziening. Er zijn boilers die op het dak zijn geïnstalleerd en worden verwarmd door de zon. Maar in de winter is de zon niet voldoende om de watertank te verwarmen. Het appartement heeft een schakelaar die het verwarmingselement in de tank start. Het eerste ongemak is dat je het van tevoren moet inschakelen. Een half uur tot een uur voordat je gaat douchen. 's Avonds is dit scenario nog acceptabel, maar 's ochtends zul je nooit warm water hebben. Ten tweede kun je het gemakkelijk vergeten uit te zetten. Met als resultaat - een doorgebrand verwarmingselement en een elektriciteitsrekening.

Overigens is elektriciteit hier erg duur, en je moet er elke 2 maanden voor betalen. Het is op dit moment onmogelijk om de belangrijkste verbruiker te bepalen. Het zou handig zijn om statistieken te hebben over de belangrijkste elektrische verbruikers, zoals airconditioning, vloerverwarming, verlichting, enz. Met realtime gegevens over het stroomverbruik bij de hand, kun je in ieder geval beginnen met analyseren waar het aan wordt besteed.

## Essentiële componenten van een slim huis: schakelaars, sensoren en slimme meters

Het blijkt dat de eerste kandidaten voor slimme apparaten verschillende schakelaars en stroomverbruiksmonitoring zijn. Daarna zul je waarschijnlijk nadenken over het regelen van de airconditioner en vloerverwarming volgens een schema of volgens temperatuurmetingen. Dit betekent dat we temperatuur- en vochtigheidssensoren, relais voor het regelen van vloerverwarming en IR-afstandsbedieningen voor airconditioners nodig zullen hebben. Elk huis heeft ook ramen, en de ramen hebben meestal gordijnen - het zou handig zijn als de gordijnen automatisch sluiten als je naar bed gaat. Zo vormen schakelaars, sensoren en slimme meters de basis van een slim huis. En dan kun je dromen op basis van specifieke behoeften.

## Het kiezen van de juiste slimme huisoplossing: KNX vs. Sonoff vs. Xiaomi

Welke slimme huis- en automatiseringsoplossingen zijn er op de markt? We kunnen denken aan KNX, dat vandaag de dag een van de meest voorkomende oplossingen is voor gebruik in middelgrote en grote automatiseringssystemen voor woningen, kantoren en commerciële ruimtes. Het is al meer dan twintig jaar op de markt en wordt nu ondersteund door veel grote fabrikanten van elektrische apparatuur. Om echter een KNX-oplossing samen te stellen, moet er veel engineeringwerk worden verricht. De belangrijkste logica wordt doorgaans samengesteld in een apart schakelbord. Als dit niet oorspronkelijk was voorzien, kan installatie in een bestaand appartement moeilijk of zelfs onmogelijk zijn zonder de juiste wijzigingen aan te brengen in de lay-out. Bovendien zijn op KNX gebaseerde oplossingen behoorlijk duur.

Een andere benadering zou kunnen zijn om apparaten te kopen van Chinese fabrikanten zoals Sonoff of Xiaomi. Hun belangrijkste voordeel is de prijs, de eenvoud van installatie en configuratie. Iedereen zal de meeste sensoren en apparaten in hun huis kunnen installeren. Op sommige plaatsen heb je misschien een elektricien nodig, bijvoorbeeld om slimme schakelaars te installeren, maar ze zullen de plaats innemen van de oude en je hoeft geen wijzigingen aan te brengen in de lay-out van het appartement. De fabrikant biedt een enkele applicatie voor het beheren van apparaten. Je moet echter altijd onthouden dat je gegevens ergens naartoe worden gestuurd naar de server, en alle communicatie met apparaten is onmogelijk zonder een internetverbinding.


## DIY slim huis: Het bouwen van een thuisserver voor volledige controle

En nog een benadering voor het bouwen van een slim huis is gebaseerd op de tweede, d.w.z. het gebruik van beschikbare apparaten van dezelfde Chinese fabrikanten, maar daarnaast een thuisserver installeren in je appartement / huis om van de clouds af te komen. Dit is de weg die we hebben gekozen in onze slimme huisoplossing. In de volgende delen zal ik gedetailleerd praten over de assemblage van onze demostand en zijn mogelijkheden.

<RoboAcademyText fWeight="500">
  Dat is alles voor nu! In de volgende les zullen we dieper ingaan op de praktische kant van het bouwen van een slim huis en laten we zien hoe je een Smart Home Board kunt assembleren. Blijf op de hoogte en maak je klaar om je eerste stap te zetten naar het creëren van een volledig functioneel en geautomatiseerd huis.
</RoboAcademyText>