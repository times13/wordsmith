
# Utilise Ubuntu comme image de base.
FROM ubuntu

# Actualise la liste des paquets disponibles.
RUN apt-get update

# Installe Maven pour construire le projet Java
# et OpenJDK 8 pour compiler et exécuter le code.
RUN apt-get install maven openjdk-8-jdk -y

# Copie le contenu du dossier words dans l'image.
# Cela comprend notamment pom.xml et src/.
COPY . .

# Construit le projet Maven, exécute les vérifications
# et produit normalement le fichier words.jar.
RUN mvn verify

# Définit le répertoire de travail pour la suite.
# Attention : le dossier de sortie Maven est target,
# et non targets.
WORKDIR target

# Lance l'application Java en limitant la mémoire
# initiale et maximale du tas à 8 Mo.
CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
