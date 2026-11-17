# Notice

Ce dépôt contient du code issu de deux projets open source, tous deux sous
licence Apache 2.0 :

| Dossier | Projet d'origine | Licence |
|---|---|---|
| `backend/` | [spring-petclinic/spring-petclinic-rest](https://github.com/spring-petclinic/spring-petclinic-rest) | Apache 2.0 (`backend/LICENSE.txt`) |
| `frontend/` | [spring-petclinic/spring-petclinic-angular](https://github.com/spring-petclinic/spring-petclinic-angular) | Apache 2.0 |

Le code applicatif appartient à ses auteurs d'origine. Le travail propre à ce
projet porte sur la plateforme DevOps : Dockerfiles, manifestes Kubernetes,
pipelines, GitOps, Terraform, monitoring et documentation. Les modifications
apportées au code applicatif (par exemple la configuration de l'URL de l'API)
sont signalées dans l'historique Git.

Les dossiers `.github` des projets d'origine ont été retirés : leurs workflows
ne s'exécutent pas dans un monorepo et seront remplacés par ceux de ce dépôt.
Le `Dockerfile`, le `.dockerignore` et le `docker-compose.yml` d'origine ont
aussi été retirés : la conteneurisation fait partie du travail de ce projet.
