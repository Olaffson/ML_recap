# Projet de prédiction de fréquentation de cinéma

Ce dossier utilise Django pour prédire le nombre d'entrées dans un cinéma, on fait le lien entre une API et une base de données déployées sur Azure.

## URL

Les URL disponibles sont les suivantes :

- `admin/` : accès à l'interface d'administration de Django.
- `login` : page de connexion.
- `signup` : page d'inscription.
- `logout/` : déconnexion de l'utilisateur.
- `prediction` : page de prédiction pour le cinéma et les estimations françaises.
- `bot` : page donnant un mini agenda de 7 jours pour optimiser les 4 salles réservées.
- `prediction_VS_reel` : envoie dans la base de données les chiffres du cinéma.
- `scraping/` : page de scraping.
- `delete_data/` : suppression des données.
- `video/` : page vidéo.

## Fonctionnalités

- La page `prediction` donne les prédictions pour le cinéma et les estimations françaises. Elle fait le lien entre une API et une base de données Azure.
- La page `bot` donne un mini agenda de 7 jours pour optimiser les 4 salles réservées.
- La page `prediction_VS_reel` envoie dans la base de données les chiffres du cinéma.

## Configuration

Les secrets ne sont plus écrits dans le code : ils sont lus depuis les variables d'environnement ou depuis un fichier `cine_prediction/.env` non versionné. Copiez `.env.example` en `.env` et remplissez les valeurs :

- `DJANGO_SECRET_KEY` (obligatoire) : clé secrète Django. Pour en générer une : `python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"`.
- `DJANGO_ALLOWED_HOSTS` : hôtes autorisés, séparés par des virgules.
- `DB_SERVER`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`, `DRIVER` : connexion à la base Azure SQL.
- `TMDB_API_KEY` : clé de l'API TMDB utilisée par le spider `allocine_sortie`.
