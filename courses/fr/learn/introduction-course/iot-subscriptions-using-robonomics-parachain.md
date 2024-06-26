---
title: "Leçon n°5, Abonnements IoT en utilisant Robonomics Parachain"
lastUpdate: Thu May 04 2023 12:53:55 GMT+0400 (Samara Standard Time)
description: Vous apprendrez comment acheter un abonnement IoT sur Robonomics Parachain en utilisant de vrais jetons de notre réseau.
lessonNumber: 5
metaOptions: [Apprendre, Introduction aux idées de Robonomics]
defaultName: Introduction to the ideas of Robonomics
---

La dernière leçon de notre Cours d'Introduction est très probablement la plus difficile, car elle nécessitera de la patience de votre part. Vous apprendrez comment acheter un abonnement IoT sur Robonomics Parachain en utilisant de vrais jetons de notre réseau.


## Intro

Un abonnement IoT est une clé d'accès à toutes les fonctions liées à la modification de l'état du jumeau numérique d'un système cyber-physique et au stockage d'infoumations à ce sujet en utilisant l'écosystème Polkadot / Kusama. Posséder un abonnement dispense l'utilisateur de devoir payer des frais de transaction. Au lieu de cela, l'utilisateur peut envoyer une transaction gratuite une fois dans un certain laps de temps.

Le principal moyen d'acheter un abonnement est de participer à la vente aux enchères d'abonnements, et donc dans cette leçon, vous devriez obtenir des jetons XRT pour faire des offres et soumettre des transactions. Plus d'infoumations sur ce processus sont également disponibles sur [notre wiki](https://wiki.robonomics.netwouk/docs/get-subscription).

## Instructions

<List type="numbers">

<li>

Vous avez besoin d'environ 2 jetons XRT Robonomics Parachain ([à propos du jeton](https://robonomics.network/xrt/)). Si vous ne les avez pas, vous avez plusieurs options :

a) Si vous réussissez les deux tests après la Leçon 2 et la Leçon 4 avec 90% de bonnes réponses, vous pouvez demander des jetons gratuits pour la leçon. Vérifiez vos scores sur [l'application de vérification spéciale](https://lk.robonomics.academy/). En particulier, vous devez obtenir 15 sur 17 pour la Leçon 2 et 10 sur 11 pour la Leçon 4, et vous avez deux tentatives pour le faire. Pour obtenir des jetons, contactez l'Administrateur de l'Académie sur notre [Discord](https://discord.gg/xqDgG3EGm9) (IBerman#5862).

b) Achetez des jetons XRT sur l'une des bourses (consultez la [liste des bourses](https://www.coingecko.com/en/coins/robonomics-network#markets/)). Soyez prudent si vous n'êtes pas familier avec les bourses de cryptomonnaies, rappelez-vous que tous les achats sur les bourses de cryptomonnaies peuvent comporter des risques potentiels, n'achetez que la quantité de jetons nécessaire pour passer cette leçon. Gardez également à l'esprit que Robonomics existe sur deux réseaux, Ethereum et Kusama, donc chaque réseau a son propre jeton XRT. Vous avez besoin d'un jeton utilisé par la parachain dans le réseau Kusama.

c) Si vous avez un jeton XRT sur le réseau Ethereum (format ERC-20), utilisez le processus [Exodus](https://old.dapp.robonomics.network/#/exodus) pour transférer des jetons du réseau Ethereum à Kusama. Gardez à l'esprit que le transfert de jetons est effectué une fois par semaine.

</li>

<li>

Les abonnements IoT sont achetés par le biais d'un processus d'enchères, le plus offrant obtenant un abonnement.

Avant d'essayer de participer à l'enchère, vous devriez vérifier s'il y en a de disponibles. Ouvrez le portail Robonomics [Polkadot/Substrate](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkusama.rpc.robonomics.network%2F#/chainstate) avec le menu État de la chaîne. Sélectionnez la requête <code>rws</code> avec <code>auctionQueue()</code> et appuyez sur le bouton '+'. Vous devriez voir les ID des enchères disponibles ; retenez l'ID de l'une d'entre elles. Si aucune enchère n'est affichée ou disponible, veuillez nous contacter sur notre Discord dans le canal "[🎓robonomics-academy](https://discord.com/channels/803947358492557312/803947358492557315)".

Maintenant, sur le même menu État de la chaîne, sélectionnez <code>rws</code> avec <code>auction(u32): Option&lt;PalletRobonomicsRwsAuctionLedger&gt;</code> et dans les champs <code>u32</code> entrez l'ID de l'enchère mémorisée. Après avoir appuyé sur le bouton "+", vous verrez des informations sur une enchère intéressante. Si le champ <code>winner</code> a une valeur <code>null</code>, alors personne n'a cet abonnement et vous pouvez essayer de l'obtenir.

</li>

<li>

Faites une offre avec vos jetons XRT.

Allez dans le menu Développeur -> Extrinsic et choisissez le même compte Polkadot.js que celui que vous avez utilisé dans la leçon précédente extrinsèque <code>rws</code> avec <code>bid(index, amount)</code>. Dans le champ <code>index</code>, saisissez l'ID de l'enchère intéressante. Dans le champ <code>amount</code>, vous devez saisir votre nombre de jetons pour l'enchère, converti en "wieners" (1 XRT = 1 000 000 000 Wn). Vérifiez le prix minimum actuel de l'abonnement dans notre [dapp](https://dapp.robonomics.network/#/subscription). 

Soumettez la transaction et si vous avez de la chance, vous obtiendrez l'abonnement IoT. Vous pouvez vérifier que votre adresse Polkadot possède l'abonnement via le même menu État de la chaîne.

</li>

<li>

La dernière étape consiste à ajouter des appareils à votre abonnement IoT.

Cela signifie simplement que vous attribuez des adresses Polkadot supplémentaires à votre abonnement afin qu'elles puissent exécuter des extrinsèques (par exemple, pour lancer des appareils ou envoyer des données d'appareils à la blockchain).

Tout d'abord, créez un nouveau compte pour Robonomics Parachain (guide sur [notre wiki](https://wiki.robonomics.network/docs/create-account-in-dapp/)), et appelez-le "smart device" pour plus de commodité.

Ensuite, allez dans le menu Développeur -> Extrinsic, et sélectionnez <code> rws</code> avec <code>setDevices()</code>. Dans la liste des appareils, utilisez le bouton "Ajouter un élément" pour ajouter des appareils et sélectionnez un compte récemment créé. Ensuite, soumettez la transaction.

L'adresse de l'appareil doit être ajoutée à l'abonnement. Vous pouvez le vérifier dans le menu État de la chaîne via la requête <code>rws</code> avec <code>devices()</code> pour votre compte Polkadot.js qui possède l'abonnement.

</li>

</List>

<Result>

La leçon sera considérée comme terminée après l'envoi d'une transaction réussie pour l'achat d'un abonnement IoT et l'ajout d'un appareil pour celui-ci. Les transactions devraient apparaître dans l'explorateur Polkadot pour votre compte.

Vous pouvez vérifier vos résultats sur [l'application de vérification spéciale](https://lk.robonomics.academy/). Pour vous authentifier sur l'application de vérification, utilisez le même compte dans Polkadot.js qui a été utilisé pendant le cours.

</Result>