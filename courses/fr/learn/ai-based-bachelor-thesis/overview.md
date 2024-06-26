---
title: Aperçu
description: Démarrer rapidement votre thèse de licence avec des outils alimentés par l'IA
metaOptions: [Apprendre, Démarrer rapidement votre thèse de licence avec des outils alimentés par l'IA]
defaultName: Quickstart Your Bachelor's Thesis with AI-powered Tools
---

<RoboAcademyText fWeight="500">
Alors, ce que vous redoutiez est arrivé.
</RoboAcademyText>

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmW6qohyJvUF2c3EwhVWZXghArAZQ6KkBsbqT41QRgJRAh', type: 'webm'}]" />

Vous devez soumettre un travail textuel volumineux et la date limite est très proche. Ou peut-être que la situation est différente : la date limite de soumission n'est peut-être pas si effrayante, mais écrire de gros documents, surtout avec un contenu formel et technique, vous fait grimacer et repousser la tâche pendant longtemps. D'une manière ou d'une autre, vous devez passer par un processus assez long, monotone et souvent très ennuyeux qui assombrit votre motivation. Peut-être aimeriez-vous consacrer plus de temps à des tâches créatives et de développement, mais malheureusement, certaines professions et activités sont structurées de cette manière.

## Entrer dans l'IA

Heureusement pour nous tous, le progrès qui a rendu nos tâches quotidiennes plus faciles tout au long de l'histoire a atteint le domaine de l'écriture de textes. Cette fois, c'est possible grâce aux avancées en intelligence artificielle, en particulier aux modèles de langage génératif, capables de comprendre et de résoudre des demandes et de fournir des réponses plus ou moins significatives sous forme de chat. Chez Robonomics, nous ne pouvions tout simplement pas ignorer quelque chose qui pourrait élever le niveau d'automatisation dans la communication et l'interaction entre les êtres vivants et les machines (et rendre nos tâches quotidiennes plus faciles aussi !).

Les derniers modèles GPT impressionnent par leurs capacités, mais la question se pose de savoir comment les utiliser correctement et, surtout, dans quelle mesure on peut leur faire confiance. Ces compétences sont appelées ingénierie de la demande, et dans ce but, nous présentons ce guide, qui vous poussera vers une compréhension de base des possibilités de l'intelligence artificielle générative actuelle.

Dans ce guide, nous essaierons d'écrire une simple thèse de licence, basée sur la branche de connaissance de notre "bachelier" et le matériel de départ que le bachelier a passé. Nous essaierons certainement de respecter les règles académiques minimales, mais deux semaines (qui est le temps prévu pour ce guide) ne suffisent certainement pas pour considérer la thèse de licence comme réussie (bien que la réalité prouve parfois le contraire). 

Néanmoins, ce guide peut être considéré comme un bon point de départ pour comprendre quels sont les processus les plus routiniers et les plus chronophages que l'IA peut déjà lisser. Au fait, vous n'avez pas à vous limiter à une tâche de thèse de licence : ce guide sera utile pour tout travail textuel suivant la norme IMRaD (Introductionductionductionductionductionductionduction, Méthode, Résultats, Discussion) : publications de journaux et de conférences, thèses de doctorat, rapports techniques, manuels, etc.

<RoboAcademyNote title="DISCLAIMER" type="warning">
  Le guide ne garantit pas et n'a pas pour but de garantir la soumission réussie d'une thèse de licence avec une note maximale.
</RoboAcademyNote>

## Outils utilisés

Parmi les services d'IA qui ont été utilisés dans le guide :

**[ChatGPT](https://chat.openai.com/chat)** — un chatbot basé sur le modèle de langage pré-entraîné générateur de transformer (ver. 3.5 et 4) créé par OpenAI. Il fonctionne sous forme de chat avec l'utilisateur, répondant à leurs demandes qui peuvent varier des questions simples à la composition de poésie et au débogage du code utilisateur. Sa connaissance est limitée à septembre 2021, car il n'a pas accès à Internet. L'utilisation de base est gratuite, mais nécessite une inscription avec un numéro de téléphone (non disponible dans certains pays). Il dispose d'une option d'abonnement (20 $ par mois) avec des fonctionnalités plus puissantes et la possibilité d'ajouter des plugins, tels que pour l'accès à Wolfram ou Slack.

**[Bing Chat](http://www.bing.com)** — un chatbot basé sur GPT-4 intégré dans le service de recherche Bing de Microsoft. Un compte Microsoft est requis pour y accéder. Essentiellement, il a les mêmes capacités que ChatGPT, mais avec l'accès à Internet, le rendant plus puissant.

**[Auto-GPT](https://news.agpt.co/)** — un logiciel qui utilise GPT-4 pour créer des agents IA autonomes qui résolvent une tâche définie par l'utilisateur. L'agent a accès à Internet, à la mémoire à long terme et à la possibilité de sauvegarder des informations dans des fichiers, ce qui lui permet d'effectuer des séquences d'actions complexes. Pour l'utiliser, un compte sur OpenAI est requis, de préférence avec un abonnement payant. Les instructions d'installation sont [disponibles ici](https://docs.agpt.co/setup/).

**[Notion AI](https://www.notion.so/product/ai)** — un assistant IA intégré dans le logiciel de gestion des connaissances éponyme. Il a un accès gratuit limité, tandis qu'un abonnement coûte 10 $ par mois. Il est pratique pour le traitement et l'amélioration de textes déjà préparés, et dispose de fonctions préinstallées à cet effet.

De plus, nous aurons besoin des services suivants :

**[Overleaf](http://www.overleaf.com)** — Éditeur LaTeX en ligne pratique pour la mise en forme de texte. Il dispose d'un ensemble de modèles pour tout type de travail (des thèses et articles aux présentations). Nous utiliserons le [Modèle de thèse MIT](https://www.overleaf.com/latex/templates/mit-thesis-template/ytphktgwpktc).

**[Google Scholar](http://scholar.google.com)** — un moteur de recherche pour les publications scientifiques. Il est utilisé pour vérifier les sources suggérées par les services d'IA.

## Comment utiliser les outils d'IA

### Chatbots d'IA (ChatGPT, Bing)

Les chatbots d'IA (ChatGPT, Bing) ne nécessitent pas une approche particulièrement complexe : il vous suffit de formater la demande appropriée et de l'envoyer au chatbot (il n'y a qu'une limite sur le nombre de caractères par message, mais vous pouvez demander au chatbot d'attendre que tout le texte de la demande soit envoyé).

### Notion AI

Pour Notion AI, il suffit d'insérer un bloc de texte sur n'importe quelle page et d'appeler le menu contextuel avec des demandes à l'assistant IA.

### Auto-GPT

Auto-GPT nécessite une approche différente, car l'utilisateur doit spécifier avant de commencer les éléments suivants :

- Nom de l'assistant IA
- Rôle de l'assistant IA
- Jusqu'à 5 objectifs consécutifs à réaliser par l'assistant IA

Après cela, Auto-GPT lancera un agent qui affichera pour l'utilisateur toutes les "pensées" et actions effectuées, à savoir :

- `THOUGHTS` — une idée générale que l'agent veut mettre en œuvre dans l'itération actuelle
- `REASONING` — une raison pour laquelle l'agent a choisi cette idée
- `PLAN` — actions spécifiques pour réaliser l'idée (recherche sur internet, analyse de documents, écriture dans un fichier, etc.)
- `CRITICISM` — conditions spéciales que l'agent impose à ses actions (par exemple, "rechercher uniquement des références de haute qualité des revues IEEE").

## Premiers pas

<RoboAcademyNote title="WARNING" type="warning">
  Les outils d'IA sont encore en cours d'amélioration, donc vérifiez toujours les résultats que vous obtenez.
</RoboAcademyNote>

### Alimenter le service avec un contexte

Un des avantages importants des derniers services d'IA est qu'ils se souviennent assez bien du contexte d'une demande dans une seule session. Par conséquent, la première chose à faire pour commencer une thèse de bachelor est de créer un contexte (une "légende") et de le fournir au service.

Comme matériau pour le travail, le cours ["Maison intelligente souveraine avec Robonomics et Home Assistant"](/learn/smart-home-course/overview) sur Robonomics Academy a été pris comme point de départ. En conséquence, le contexte suivant a été créé :

<RoboAcademyDialog>

I am a student of the Department of IoT Engineering and Web3 Science. 

I am going to get Bachelor of Science in Computer Science and Engineering.

I completed an online course called "Smart Home Sovereign". In this course, I went through all the steps necessary to build my own sovereign smart home, the main advantage of which is the security / privacy of user data.
During the course, I set up an IoT hub on a Raspberry Pi and connected smart devices (such as a temperature/humidity sensor, a door sensor, a smart bulb, a motion sensor, etc.) to it via a Adaptateur Zigbee using the MQTT protocol. The IoT hub is powered by Home Assistant software. Next, I connected the hub to a decentralized cloud, based on Polkadot web3 technology. This is necessary to securely transfer device data to the network without the need for a centralized cloud service provider. This allows me to securely manage my home remotely.

Now I want to take this course as a basis and write a bachelor's thesis with your help.

</RoboAcademyDialog>

La réaction typique d'un chatbot d'IA à ce contexte serait de suggérer de clarifier la demande et comment le service peut aider.

### Choisir un sujet parmi les suggestions

La prochaine étape (typique pour une situation de bachelor) est de choisir un sujet pour la thèse. Ici, il suffit de faire une demande de lien `Proposer N sujets pour ma thèse`. ChatGPT et Bing Chat ont proposé ce qui suit :

<RoboAcademyDialog>

"Designing a Secure and Private Smart Home System using Web3 Technologies" — This topic could involve examining the steps you took to build your sovereign smart home and exploring the security and privacy benefits of using IoT and Web3 technologies.

"Comparing Centralized and Decentralized Approaches to Smart Home Data Management" — This topic could involve comparing and contrasting the benefits and drawbacks of using centralized cloud vendors versus decentralized cloud technologies like Polkadot for managing smart home data.

"Developing a Smart Contract-based Framework for Managing Smart Home Devices" — This topic could involve exploring the use of smart contracts to manage smart home devices and develop a secure and efficient framework for managing them.

"Investigating the Security and Privacy Risks of Smart Home Systems" — This topic could involve examining the potential risks and vulnerabilities of smart home systems, including issues related to data privacy, cybersecurity, and physical safety.

"Exploring the Role of Blockchain in Smart Home Data Management" — This topic could involve examining how blockchain technology could be used to manage smart home data and ensure the security and privacy of user data.

"Investigating the Future of Smart Home Technologies and their Impact on Society" — This topic could involve examining the potential social and economic impacts of smart home technologies, including issues related to privacy, security, and the digital divide.

</RoboAcademyDialog>

Le sujet **"Conception d'un système de maison intelligente sécurisé et privé utilisant les technologies Web3"** a été choisi pour le guide.

### Plan simple avec structure IMRaD

Ensuite, en principe, nous pouvons passer aux sections spécifiques des thèses, en suivant la structure IMRaD. Cependant, il serait bien d'avoir un plan plus détaillé pour le travail de bachelor. Cela peut également être demandé à un service d'IA. ChatGPT a suggéré le plan suivant, sans conditions supplémentaires :


<RoboAcademyDialog>

<ChatGPT/>

1. Introduction
    1. Background and motivation
    2. Research questions and objectives
    3. Significance of the study
2. Literature Review
    1. Aperçu of smart home technology and its security and privacy issues
    2. Introduction to web3 technology and its potential benefits for smart homes
    3. Existing research on using web3 technology for smart home security and privacy
3. Methodology
    1. Description of the smart home system design using web3 technology, including hardware and software components
    2. Implementation details and justification for design choices
    3. Evaluation plan for assessing the security and privacy of the system
4. Results and Analysis
    1. Evaluation of the implemented system with respect to security and privacy metrics
    2. Comparison with existing solutions and analysis of strengths and weaknesses
    3. Discussion of limitations and potential areas for improvement
5. Conclusion and Future Work
    1. Summary of the study's contributions and main findings
    2. Implications and significance of the results for the smart home industry and related fields
    3. Recommendations for future research and development
6. Références

</RoboAcademyDialog>

<RoboAcademyText>
Avec cette préparation terminée, nous pouvons maintenant passer à la première section de la thèse — l'Introduction.
</RoboAcademyText>
  

