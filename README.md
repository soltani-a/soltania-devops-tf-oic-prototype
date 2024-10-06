# My OIC Project

## Introduction

Ce repository est un POC démontrant la gestion du développement d'un job Oracle Integration Cloud (OIC) comme un projet Java. Il utilise Maven pour construire un fichier `.iar` (Integration Archive) à partir des sources, et un workflow GitHub Actions pour l'intégration continue et le déploiement.

## Structure du Projet

Le projet est structuré de la manière suivante :

- **`src/main/integration`** : Contient les fichiers de configuration et le processus BPEL pour l'intégration OIC.
- **`src/main/resources`** : Contient les ressources partagées telles que les schémas XSD ou les fichiers de configuration supplémentaires.
- **`src/main/manifest`** : Contient le fichier `manifest.json` qui décrit les composants de l'intégration.
- **`.github/workflows`** : Contient le fichier de workflow GitHub Actions `build-and-deploy.yml` pour l'intégration continue, le packaging en `.iar`, et le déploiement.

## Prérequis

Assurez-vous d'avoir les éléments suivants installés pour pouvoir exécuter le projet :

- [Maven](https://maven.apache.org/)
- [Java 11+](https://adoptium.net/)

## Compilation et Packaging

Pour compiler le projet et générer le fichier `.iar`, utilisez la commande suivante :

```bash
mvn clean package
```

Le fichier `.iar` généré sera disponible dans le répertoire `target` avec le nom `my-oic-project-1.0.0.iar`.

## Workflow GitHub Actions

Ce projet utilise un workflow GitHub Actions qui réalise les actions suivantes :

1. **Compilation et Packaging** : Le workflow compile le projet et génère un fichier `.iar`.
2. **Publication vers Nexus** : Le fichier `.iar` est envoyé dans un repository Nexus.
3. **Déploiement** : Le fichier `.iar` est déployé sur une instance Oracle Integration Cloud (OIC) après approbation manuelle.

Le fichier de workflow est disponible ici : [build-and-deploy.yml](https://github.com/your-repo/my-oic-project/blob/main/.github/workflows/build-and-deploy.yml).

## Fichiers Importants

Voici les principaux fichiers du projet avec leur description :

- [`pom.xml`](https://github.com/your-repo/my-oic-project/blob/main/pom.xml) : Configuration Maven du projet.
- [`src/main/integration/integration.xml`](https://github.com/your-repo/my-oic-project/blob/main/src/main/integration/integration.xml) : Configuration de l'intégration OIC.
- [`src/main/resources/example_resource.xsd`](https://github.com/your-repo/my-oic-project/blob/main/src/main/resources/example_resource.xsd) : Schéma XSD utilisé dans l'intégration.
- [`src/main/manifest/manifest.json`](https://github.com/your-repo/my-oic-project/blob/main/src/main/manifest/manifest.json) : Manifest JSON décrivant le contenu de l'archive `.iar`.

## Déploiement Manuel

Après le build, vous pouvez déployer manuellement le fichier `.iar` dans Oracle Integration Cloud à l'aide de l'interface OIC ou en utilisant un outil de ligne de commande (cURL, Postman).

## Configuration des Secrets GitHub

Le workflow utilise des secrets GitHub pour accéder aux services externes. Les secrets à configurer sont :

- `NEXUS_USERNAME`
- `NEXUS_PASSWORD`
- `OIC_USERNAME`
- `OIC_PASSWORD`
- `OIC_INSTANCE_URL`

Configurez ces secrets dans les paramètres de votre dépôt avant d'exécuter le workflow.

## Liens Utiles

- [Oracle Integration Cloud Documentation](https://docs.oracle.com/en/cloud/paas/integration-cloud/index.html)
- [Maven Documentation](https://maven.apache.org/guides/index.html)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

Pour plus d'informations sur ce projet, n'hésitez pas à me contacter ou à ouvrir une issue dans le dépôt.
