---
layout: archive
title: "Réseau arthur.com"
permalink: /portfolio/
author_profile: true
---

Bienvenue sur la page d'accueil du rapport individuel d'Arthur WAMSTER

![Topologie du Réseau](/images/Arthur.png){: style="width: 100%; margin:auto; display:block;"}

## Choix

J'ai fait le choix de configurer le proxy, le DNS et le DHCP directement sur le routeur. Cela permet d'uniformiser le réseau : chaque machine suit les mêmes règles définies par un point central. Cela facilite également le travail de l'administrateur réseau, car toutes les configurations se trouvent au même endroit. 

Seul le serveur web a été configuré sur la DMZ. Il n'a pas été mis sur le routeur car un routeur n'a pas ce rôle. L'ajouter pourrait perturber ses fonctions de base. De plus, si le serveur est compromis, l'attaquant pourrait prendre le contrôle du routeur et des réseaux associés. De la même manière, mettre le serveur sur le NAT est risqué, car si le serveur est compromis, un attaquant aurait accès au réseau privé, qui contient potentiellement des données sensibles. En outre, mettre le serveur web sur une machine qui change fréquemment d'adresse IP n'est pas très pratique.

J’ai choisi de configurer tous les services sur le routeur, notamment le DNS et le DHCP, car cela me semblait être la solution la plus simple : chaque machine n’a qu’à renseigner le routeur pour toutes les requêtes. Le serveur web a été configuré sur une machine dédiée, située dans un sous-réseau DMZ distinct de celui du LAN.

---

## Difficultés

Étant donné que je n'ai que très rarement configuré des réseaux, chaque action qui aurait normalement pris 5 minutes m'a pris une éternité :

- Plusieurs heures pour configurer et installer correctement VirtualBox et 3 VM.
- Plusieurs heures pour configurer leurs adresses IP.
- Plusieurs heures pour configurer un DNS.
- Et encore un peu de temps pour installer le serveur web, le reverse proxy et les règles de routage.

Je n’ai jamais mis de réseau en place avant ce projet alors bien que connaissant la théorie, j’ai eu énormément de mal à la mettre en pratique et heureusement qu’un camarade de mon groupe m’a aidé, car chaque étape me semblait simple mais chaque bug me prenait des heures à résoudre par méconnaissance.

Comme j’avais fait très peu de réseau avant d’arriver à l’ENSEEIHT, j’ai eu beaucoup de difficultés à mettre ce réseau en place, étant donné que je ne l’avais jamais fait. J’ai donc rencontré des difficultés à chaque étape de la mise en place du réseau, car je devais apprendre comment le faire au fur et à mesure.

Avec tout ce temps perdu, je n'ai pas eu le temps de configurer des règles de routage qui filtrent correctement les communications, et je n’ai pas eu le temps de comprendre en détail (pendant la réalisation du projet) le rôle du proxy.

---

## Solutions

Une des solutions qui m’a fait gagner du temps a été de faire un schéma détaillé de mon réseau avec les différentes adresses IP.

Pour surmonter les obstacles, je cherchais sur Internet les informations dont j’avais besoin et, si je n’y arrivais pas, je demandais de l’aide à un camarade de mon groupe qui avait de bonnes connaissances en réseau.

Pour essayer de me simplifier au maximum la charge, j’ai essayé d’adopter la même configuration que mon camarade qui m’aidait et d’aller toujours à l’essentiel comparé à ce qu’il mettait en place qui était bien trop complexe pour moi. Je souhaitais mettre en place un réseau qui fonctionne avant d’aller plus loin et de commencer à le complexifier, mais je n’en ai pas eu le temps et j’ai terminé la partie essentielle à peine quelques heures avant la présentation, pas encore connecté avec mes camarades.

---

## Points intéressants

J'ai trouvé ce projet très formateur et intéressant pour la suite. Cela m'a donné envie de configurer un site web accessible depuis le WiFi de chez moi.

Après avoir fini ce projet, je me suis rendu compte que devoir chercher par moi-même comment réaliser les différentes étapes de la mise en place du réseau avait été très formateur. Je pense que je serais désormais capable de le refaire tout seul.

Après avoir terminé le projet, je pense bien mieux le comprendre et malgré le mal que j’ai eu pour le terminer : je suis certain d’en sortir un plus motivé et plus intéressé par la matière.

