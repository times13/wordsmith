
# Utilise l'image officielle PostgreSQL.
# Elle contient déjà le serveur de base de données.
FROM postgres

# Autorise l'authentification sans mot de passe.
# Uniquement pour cet exercice, jamais en production.
ENV POSTGRES_HOST_AUTH_METHOD=trust

# Copie le script SQL dans le répertoire d'initialisation.
# PostgreSQL l'exécutera au premier démarrage avec
# un répertoire de données vide.
COPY words.sql /docker-entrypoint-initdb.d/

# Documente le port par défaut de PostgreSQL.
EXPOSE 5432