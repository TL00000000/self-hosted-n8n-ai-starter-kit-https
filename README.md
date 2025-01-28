# self-hosted-n8n-ai-starter-kit-https

n8n-https-docker
│── certs/                 # Ordner für Zertifikate
│── docker-compose.yml      # Docker Compose Setup für n8n mit HTTPS
│── .env.example            # Beispiel-Umgebungsdatei
│── README.md               # Anleitung zur Installation und Nutzung


self-hosted-n8n-ai-starter-kit-https

# n8n mit HTTPS in Docker

Dieses Repository stellt ein `docker-compose` Setup für n8n mit HTTPS bereit. Es nutzt **selbstsignierte Zertifikate** und **PostgreSQL** als Datenbank.

## 🔥 Funktionen
✅ Automatische Einrichtung von **PostgreSQL**  
✅ **HTTPS-Unterstützung** mit selbstsigniertem Zertifikat  
✅ **Dockerized** für einfache Bereitstellung  
✅ Bereit für **n8n Workflows**  

---

## 🛠 Voraussetzungen

Bevor du startest, stelle sicher, dass du folgende Software installiert hast:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)
- [OpenSSL](https://www.openssl.org/)

---

## 📌 Installation

### 1️⃣ **Projekt klonen**
```sh
git clone https://github.com/DEIN_GITHUB_USERNAME/n8n-https-docker.git
cd n8n-https-docker



2️⃣ .env Datei anlegen
Kopiere die Beispieldatei und passe sie an:


cp .env.example .env
nano .env



🔐 Zertifikat erstellen
Erstelle ein selbstsigniertes Zertifikat für HTTPS:

sh
Kopieren
Bearbeiten

mkdir -p certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout certs/n8n.key -out certs/n8n.crt \
    -subj "/C=DE/ST=Hessen/L=Frankfurt/O=Max Mustermann/OU=IT/CN=n8n.local"

