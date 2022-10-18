---
marp: true
theme: gaia
markdown.marp.enableHtml: true
paginate: true
---
<!-- backgroundImage: "linear-gradient(to bottom, #ffb7c5, #DCD0FF)" -->

<!--
_color: black
-->

# Présentation Brief 6
#### Déploiement automatique du service applicatif Voting App avec Kubernetes
Dunvael 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![width:700px height:300px](https://user-images.githubusercontent.com/108001918/196371502-28afc546-3750-413a-96e8-906997f36605.png)


<!-- paginate: false -->

---
# SOMMAIRE  
1 - Ressources utilisées
2 - Topologie
3 - Nombre de scripts
4 - Plan projet prévu VS plan projet exécuté
5 - Tâches supplentées
6 - Compréhension des outils et des logiciels
7 - Difficultés rencontrées
8 - Solutions trouvées
9 - Bonus


<!-- paginate: true -->
<!--
_color: black
-->

---
## 1 - Ressources utilisées  
* Documentation Microsoft Azure
* Documentation Kubernetes
* Portail Azure pour l'interface graphique
* Cloudshell du portail Azure
* Moteur de recherche Google
* Visual Studio Code
* Github
* *L'aide précieuse de Luna et Quentin*

<!--
_color: black
-->

---
## 2 - Topologie

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![width:500px height:500px](https://user-images.githubusercontent.com/108001918/196372669-f0cf2f50-dd24-4ff1-88b6-ed350f2249f7.png)

<!--
_color: black
-->

---
## 3 - Nombre de scripts

Un script principal et un script de suppression des ressources présents dans les deux parties.

Plusieurs scripts pour la part 2 afin de pouvoir tester et m'assurer que chaque manifest fonctionne.
Permet de  définir et d'enchaîner les étapes importantes du brief 6, mais aussi de faciliter la lisibilité et la modification des scripts.
* Part 1 : un script principal
* Part 2 : deux scripts Ingress, un script Issuer, un script principal, un script Certif, un script auto-scaling, le graph loadtester
  
<!--
_backgroundColor: black
_color: black
-->

--- 
## 4 - Plan projet prévu VS plan projet exécuté 
|  | *Plan projet prévu* | *Plan projet exécuté* |
|-----------|:----------:|:------------:|
| GR|&#9745;|&#9745;|
| Clés SSH |&#9745;|&#9745;|
| Images container |&#9745; |&#9745;|
| Load Balancer |&#9745;|&#9745;|
| ClusterIP |&#9745;|&#9745;|
| Secret Kubernetes |&#9745;|&#9745;|
| Storage account |&#9745;|&#9745;| 

<!--
_color: black
-->

--- 
|  | *Plan projet prévu* | *Plan projet exécuté* |
|-----------|:----------:|:------------:|
| Persistent Volume |&#9745;|&#9745;|
| Persistent Volume Claim |&#9745;|&#9745;|
| Ingress |&#9745;|&#9745;|
| Nginx |&#9745;|&#9745;|
| Cert-manager |&#9745;|&#9745;|
| Certificat TLS |&#9745;|&#9745;|
| DNS |&#9745;|&#9745;|
| Load tester |&#9745;|&#9745;|
<!--
_color: black
-->

--- 

|  | *Plan projet prévu* | *Plan projet exécuté* |
|-----------|:----------:|:------------:|
| Executive summary |&#9745;|&#9745;|
| DAT |&#9745;|&#9745;|
| Explications fonctionnement Kubernetes |&#9745;|&#9745;|
| Méthodologie Scrum |&#9745;|&#9745;|

<!--
_color: black
-->

---
## 5 - Tâches supplentées

Certaines tâches de la partie 2 du Brief 6 ont été supplentées afin de palier le manque de temps et permettre de réaliser les bonus.
* App Gateway
* Agic-on
* Certbot

<!--
_color: black
-->

---
## 6 - Compréhension des outils et des logiciels
***Terraform*** = 
* outil organisé qui convient pour déployer pas à pas une infrastructure et des applications.
* construction d'un plan prédéfini des étapes qui vont se réaliser en parallèle avec des messages d'erreur détaillés et précis.
* permet de configurer et paramétrer toutes les étapes d'une infrastructure.
* compatible avec d'autres logiciels et plateformes
* un interpréteur qui reçoit du code et le transforme en différentes commandes.

<!--
_color: black
-->

---

***Ansible*** = 
* fichier père qui va appeler plusieurs fichiers fils pour chaque fonction voulue. 
* Il faut un fichier différent pour chaque étape.
* un programme qui permet d'automatiser des tâches.
* prend en entrée une liste d'actions dans l'ordre au format YAML (pas un résultat fini comme terraform)
* il exécute du code python en sortie = des possibilités infinies car l'utilisateur peut installer des collections (pleins de fonctions qu'Ansible va pouvoir exécuter).

<!--
_color: black
-->

---
## 6 - Difficultés  rencontrées
Nous avons rencontré plusieurs difficultés : communes et individuelles.

* Prioriser les différentes étapes du script en fonction de leurs pré-requis
* Rechercher et analyser de la documentation (Ansible mal rédigée, Ansible et Azure presque incompatibles, mauvaise adaptabilité et flexibilité du logiciel d'ansible, documentations pas à jour)
* Trier les informations, les gérer et les assembler

<!--
_color: black
-->

---
## 7 - Solutions trouvées 
Afin de palier aux difficultés, nous avons cherché des solutions, nous sommes remis en question et avons adoptés différents comportements :

* scrums quotidiens
* écoute active 
* communication permanente 
* des temps/moments dédiés
=> ont permis d'apprendre à travailler ensemble de manière optimale et convenable pour tous les membres du groupe. 

<!--
_color: black
-->
---
## 8 - Bonus

Example de nos courbes graphiques en temps réel
&nbsp;&nbsp;&nbsp;&nbsp;![width:1100px height:500px](https://user-images.githubusercontent.com/108002178/192768326-e169f53b-b6e8-422c-983c-d68fafe29c15.jpg)

<!--
_color: black
-->

---

&nbsp;&nbsp;&nbsp;&nbsp;![width:1100px height:600px](https://user-images.githubusercontent.com/108002178/192768327-7a2c27bd-5b2f-48ac-9b6e-af83723e7f95.jpg)

<!--
_color: black
-->
