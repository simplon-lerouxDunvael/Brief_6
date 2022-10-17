# Document d'architecture technique.
## Besoins fonctionnels.
Les utilisateurs doivent pouvoir voter sur l'application votingApp.
- votingApp doit être hautement disponible.

## Besoins non-fonctionnels.
| Element | Valeur | Commentaires |
| ------- | ------ | ------------ |
| Provider | Azure | Choix stratégique |
| Service | AKS | Choix stratégique |
| Gateway | Ingress | |
| Serveur | Nginx |
| BDD | Redis | |
| Application | VotingApp | Doit pouvoir scaleout et disposer d'un nom de domaine |

## Représentation fonctionnelle.
![](diagram.jpg)

### Listes des environnements.
| Nom | Type | Caractéristiques |
| --- | ---- | ---------------- |
| Azure | Provider | |
| aks | Kubernetes Cluster | Cluster k8s Azure |

## Représentation applicative.
![](diagram2.jpg)

### La matrice de flux.
| Source | Réseau | Destination | Protocol | Port |
|------------- | ------ | ----------- | -------- | ---- |
| Ingress Gateway | virutal-network | Service votingApp | TCP | 80 |
| Service votingApp | virutal-network | Pods votingApp | TCP | 80 |
| Service Redis  | virutal-network | Pod Redis | TCP | 6379 |
| Service votingApp | virtual-network | Service Redis | TCP | 6379 |
## Représentation infrastructure.
![](diagram3.jpg)
## Représentation opérationnelle.
![](diagram4.jpg)
## Décision d'architecture.
| Sujet | Contenue |
| ----- | -------- |
| Décision d'architecture | Utilisation d'un gateway |
| Problématique | Quels Gateway utiliser ? |
| Hypothése | L'application utilise une gateway |
| Alternative | Option 1 : Utilisation de Ingress dans kubernetes <br> Option 2: Utilisation de la gateway Azure |
| Decision | Option 1 |
| Justification | L'daptation sur d'autre cloud provider |
| Implication | Génération et implémentation du certificat TLS avec kubernetes |



