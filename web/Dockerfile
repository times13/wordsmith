
# Image de base : le conteneur utilisera Ubuntu.
FROM ubuntu

# Empêche certaines installations de demander une réponse interactive.
ENV DEBIAN_FRONTEND=noninteractive

# Actualise la liste des paquets disponibles.
RUN apt-get update

# Installe le compilateur Go pour construire notre application.
RUN apt-get install -y golang-go

# Définit /app comme répertoire de travail dans l'image.
WORKDIR /app

# Copie les fichiers du dossier web vers /app dans l'image.
# Cela inclut dispatcher.go et le dossier static/.
COPY . .

# Compile le code Go et place l'exécutable à un chemin précis.
# -o : précise le nom et l'emplacement du fichier de sortie.
# /dispatcher : signifie que l'exécutable sera placé à la racine du système de fichiers du conteneur.
RUN go build -o /dispatcher dispatcher.go

# Indique le port utilisé par l'application (documentation uniquement).
EXPOSE 80

# Lance l'exécutable lorsque le conteneur démarre.
CMD ["/dispatcher"]
