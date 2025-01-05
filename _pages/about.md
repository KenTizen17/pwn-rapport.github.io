---
permalink: /
title: "Rapport de Projet: Création d'un Réseau d'Entreprise sous Machines Virtuelles"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


## Architecture

Chaque étudiant a configuré un réseau interne comprenant :

1. **Une VM Routeur :**
    - Fonctionnalités : DHCP pour le LAN, DNS, et reverse proxy (Nginx).
    - Interfaces :
        - Interface publique pour l'interconnexion avec d'autres réseaux.
        - Interface privée pour le LAN et la DMZ.
2. **Une VM pour la DMZ :**
    - Hébergement du serveur web Apache.
3. **Une VM pour le LAN :**
    - Utilisée pour simuler les utilisateurs internes.

### Diagrammes d'architecture

#### Architecture individuelle

Retrouvez les architectures individuelles en naviguant entre les onglets
#### Interconnexion des réseaux

L'interconnexion entre les réseau de chaque entreprise c'est faite via wifi (SKYNET), le réseau wifi SKYNET à été mis en place à l'aide d'une rasberry pi5

Ci-dessous le schéma de cette interconnexion

![Topologie du Réseau](/images/archi-fi.png){: style="width: 200%; margin:auto; display:block;"}
---

## Principaux choix effectués

- **Plan d'adressage :**
    - Adresses privées pour le LAN et la DMZ.
    - Une adresse publique pour l'interface d'interconnexion de chaque routeur.
- **Protocole DHCP :**
    - Configuration des machines du LAN via DHCP pour simplifier l'administration.
- **Serveur DNS :**
    - Mise en place d'un DNS local pour chaque réseau pour gérer le nommage interne.
- **Reverse Proxy (Nginx) :**
    - Pour faciliter l'accès aux services web dans la DMZ sans exposer directement le serveur Apache.
- **Sécurité :**
    - Configuration de pare-feux avec iptables sur les routeurs pour filtrer le trafic entrant et sortant.
- **Réseau Wi-Fi SKYNET :**  
    - Chaque entreprise a été connectée à un réseau wifi SKYNET, permettant l'interconnexion entre les différentes entreprises.

---

## Difficultés rencontrées

- **Problème de routage entre les réseaux :**
    - Initialement, certains paquets ne parvenaient pas à atteindre les réseaux voisins.
- **Configuration du DNS :**
    - Gestion de la hiérarchie DNS et propagation des enregistrements dans un contexte multi-réseaux.
- **Reverse Proxy :**
    - Configuration des redirections pour les différentes ressources de manière optimale.

## Solutions

- **Problème de routage :**
    - Ajout de routes statiques sur les routeurs.
    - Vérification des tables de routage avec `ip route`.
- **Configuration DNS :**
    - Utilisation d'une structure hiérarchique pour les noms de domaines.
    - Test des requêtes avec `dig` et `nslookup` pour vérifier la résolution.
- **Reverse Proxy :**
    - Configuration fine des hôtes virtuels dans Nginx pour rediriger les requêtes HTTP vers les serveurs appropriés.

---

## Points intéressants

- **Visualisation des protocoles avec Wireshark :**
    - Observation des échanges DNS, DHCP, et HTTP en temps réel.
- **Sécurisation avec iptables :**
    - Application des règles `stateful` pour autoriser les connexions déjà établies.
- **Interconnexion multi-réseaux :**
    - Coordination entre les membres pour établir un plan d'adressage cohérent et des routes correctes.

---

## Conclusion

Le projet a permis de mettre en pratique les concepts théoriques des protocoles réseaux. Grâce à une démarche incrémentale, nous avons :

1. Construit des réseaux isolés et interconnectés.
2. Configuré des services essentiels comme DHCP, DNS, et un reverse proxy.
3. Amélioré nos compétences en routage, sécurité, et gestion des VMs.

**Prochaines étapes possibles :**
- Mise en place d'une solution de supervision (ex. Nagios).
- Optimisation des politiques de sécurité.

---

*Fait par : Hugo CASTELL, Alexis WAMSTER, Arthur, Ken TIZEN DJONGUE*





### Info pratiques
Le projet a permis de démontrer la faisabilité et l'efficacité de l'interconnexion de plusieurs entreprises via un réseau virtuel sous machines virtuelles. 

---

Vous pouvez consulter les différentes sections du rapport pour plus de détails sur la conception et les choix techniques. Pour toute question ou commentaire, n'hésitez pas à nous contacter.

