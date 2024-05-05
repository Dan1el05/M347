### Dockerfile Webseite 

#### Erstllen von eienm Dockerfile
 Dockerfile ist eine Textdatei, die die Schritte zum Erstellen eines Docker-Images definiert. Hier ist ein einfaches Beispiel für ein Dockerfile für eine statische Webseite:

##### Verwende ein bestehendes Image als Basis
FROM nginx:alpine

##### Kopiere den Inhalt des aktuellen Verzeichnisses in das Image-Verzeichnis
COPY . /usr/share/nginx/html

##### Setze das Arbeitsverzeichnis
WORKDIR /usr/share/nginx/html

##### Exponiere Port 80 für den Webzugriff
EXPOSE 80

##### Starte den nginx-Server im Vordergrund
CMD ["nginx", "-g", "daemon off;"]

### Erstellen einer Webseite

Legen Sie Ihre statische Webseite im gleichen Verzeichnis wie das Dockerfile ab. Stellen Sie sicher, dass Ihre Dateien im Verzeichnis html organisiert sind. Beispiel: index.html, style.css, script.js, etc.

###  Schritt 3: Erstellen des Docker-Images

docker build -t meine-webseite:latest .

docker run -d -p 8080:80 meine-webseite:latest


Testen der Webseite:Öffnen Sie einen Webbrowser und navigieren Sie zu http://localhost:8080, um sicherzustellen, dass Ihre Webseite ordnungsgemäß funktioniert.