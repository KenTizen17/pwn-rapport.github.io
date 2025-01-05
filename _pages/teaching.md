---
layout: archive
title: "Réseau alexis.com"
permalink: /teaching/
author_profile: true
---

Bienvenue sur la page d'accueil du rapport individuel d'Alexis WAMSTER

![Topologie du Réseau](/images/Alexis.png){: style="width: 100%; margin:auto; display:block;"}

## Choix

J'ai fait le choix de configurer le proxy, le DNS et le DHCP directement sur le routeur. Cela permet d'uniformiser le réseau : chaque machine suit les mêmes règles définies par un point central. Cela facilite également le travail de l'administrateur réseau, car toutes les configurations se trouvent au même endroit. 

Seul le serveur web a été configuré sur la DMZ. Il n'a pas été mis sur le routeur car un routeur n'a pas ce rôle. L'ajouter pourrait perturber ses fonctions de base. De plus, si le serveur est compromis, l'attaquant pourrait prendre le contrôle du routeur et des réseaux associés. De la même manière, mettre le serveur sur le NAT est risqué, car si le serveur est compromis, un attaquant aurait accès au réseau privé, qui contient potentiellement des données sensibles. En outre, mettre le serveur web sur une machine qui change fréquemment d'adresse IP n'est pas très pratique.

---

## Difficultés

Étant donné que je n'ai que très rarement configuré des réseaux, chaque action qui aurait normalement pris 5 minutes m'a pris une éternité :

- Plusieurs heures pour configurer et installer correctement VirtualBox et 3 VM.
- Plusieurs heures pour configurer leurs adresses IP.
- Plusieurs heures pour configurer un DNS.
- Et encore un peu de temps pour installer le serveur web, le reverse proxy et les règles de routage.

Cette perte de temps n’est pas liée à des problèmes spécifiques, mais simplement à la prise en main des outils, des concepts et à la mise en pratique.

Avec tout ce temps perdu, je n'ai pas eu le temps de configurer des règles de routage qui filtrent correctement les communications, et je n’ai pas eu le temps de comprendre en détail (pendant la réalisation du projet) le rôle du proxy.

---

## Solutions

Une des solutions qui m’a fait gagner du temps a été de faire un schéma détaillé de mon réseau avec les différentes adresses IP.

---

## Points intéressants

J'ai trouvé ce projet très formateur et intéressant pour la suite. Cela m'a donné envie de configurer un site web accessible depuis le WiFi de chez moi.
