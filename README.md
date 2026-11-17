# Plateforme DevOps pour Spring PetClinic (Java / Angular)

Projet d'apprentissage : mettre en place un cycle de vie DevOps complet autour
d'une application Java (Spring Boot) et Angular, avec Docker, Kubernetes,
CI/CD, GitOps, Infrastructure as Code, monitoring et haute disponibilité.

L'application n'est pas développée ici : elle est reprise de
[Spring PetClinic](https://github.com/spring-petclinic) (voir `NOTICE.md`).
Le travail porte sur la plateforme qui l'entoure.

## L'application

Gestion d'une clinique vétérinaire : propriétaires, animaux, visites et vétérinaires.

| Dossier | Contenu | Technologies |
|---|---|---|
| `backend/` | API REST, port 9966, chemin `/petclinic/api/` | Java, Spring Boot, Maven |
| `frontend/` | Interface web qui appelle l'API | Angular, Node.js, npm |

Base de données : H2 en mémoire par défaut, PostgreSQL via le profil `postgres`.
Les instructions de lancement d'origine sont dans `backend/readme.md` et `frontend/README.md`.

## Feuille de route

| Étape | Sujet | État |
|---|---|---|
| 1 | Dépôt, branches, versions | en cours |
| 2 | Docker et docker-compose | à faire |
| 3 | Kubernetes sur kind (Kustomize dev / prod) | à faire |
| 4 | Infrastructure as Code (Terraform) | à faire |
| 5 | CI (GitHub Actions, SonarCloud, GHCR) | à faire |
| 6 | GitOps (Argo CD) | à faire |
| 7 | Monitoring (Prometheus, Grafana) | à faire |
| 8 | Logs et alertes (Loki, Alertmanager) | à faire |
| 9 | Haute disponibilité | à faire |
| 10 | Tests et validation | à faire |

Le détail du projet (sujet, but, livrables, outils) est dans
`docs/presentation-projet-devops.pdf`.

## Branches et versions

Voir [`docs/GIT-WORKFLOW.md`](docs/GIT-WORKFLOW.md) : `main` (stable, taguée),
`develop` (intégration), `feature/*`, versions `vX.Y.Z`.
