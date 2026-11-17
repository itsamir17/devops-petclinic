# Gestion des branches et des versions

## Branches

| Branche | Rôle | Environnement visé |
|---|---|---|
| `main` | Code stable, toujours déployable. Chaque version y est taguée. | prod |
| `develop` | Intégration continue du travail en cours. | dev |
| `feature/<sujet>` | Une fonctionnalité ou une étape du projet (ex. `feature/dockerisation`). | aucun |
| `fix/<sujet>` | Correction d'un défaut sur `develop`. | aucun |
| `hotfix/<sujet>` | Correction urgente partie de `main`, fusionnée dans `main` puis `develop`. | prod |

Même en travaillant seul, on passe par des Pull Requests : c'est elles qui
déclencheront les pipelines CI (étape 5) avant toute fusion.

## Versions

- Versionnement sémantique : `vMAJEUR.MINEUR.CORRECTIF` (ex. `v1.2.0`).
- Un seul numéro pour tout le dépôt, car backend et frontend sont livrés ensemble.
- Les versions sont des **tags annotés** posés sur `main`.
- Tags d'image Docker (plus tard) : `sha-<commit>` pour dev, `vX.Y.Z` pour prod.

| Changement | Exemple |
|---|---|
| Cassant | `v1.0.0` devient `v2.0.0` |
| Nouvelle fonctionnalité | `v1.0.0` devient `v1.1.0` |
| Correction | `v1.0.0` devient `v1.0.1` |

## Messages de commit

Format « Conventional Commits » : `type(portée): description`

- Types : `feat`, `fix`, `docs`, `ci`, `chore`, `refactor`, `test`
- Portées : `backend`, `frontend`, `docker`, `k8s`, `infra`, `gitops`, `monitoring`
- Exemple : `feat(docker): ajoute le Dockerfile du backend`

## Commandes usuelles

```bash
# Démarrer un travail
git switch develop && git pull
git switch -c feature/dockerisation

# Terminer : pousser, puis ouvrir une Pull Request vers develop
git push -u origin feature/dockerisation

# Publier une version : fusionner develop dans main, puis tagger
git switch main && git pull
git merge --no-ff develop
git tag -a v0.2.0 -m "Dockerisation du backend et du frontend"
git push origin main --tags
```

## Protection des branches (à régler sur GitHub)

Dans *Settings > Branches*, pour `main` et `develop` :

- exiger une Pull Request avant fusion ;
- exiger que les vérifications CI soient vertes (à activer à l'étape 5) ;
- interdire le force-push et la suppression de la branche.
