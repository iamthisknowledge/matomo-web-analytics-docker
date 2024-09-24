
# 📊 Matomo Docker Setup | Matomo Docker-Setup

This repository demonstrates my ability to set up Matomo using Docker. It showcases my skills in configuring and running a local instance of Matomo Analytics using Docker and Docker Compose, ideal for analytics, web tracking, and data analysis.

Dieses Repository demonstriert meine Fähigkeit, Matomo mit Docker einzurichten. Es zeigt meine Fähigkeiten in der Konfiguration und dem Betrieb einer lokalen Instanz von Matomo Analytics mit Docker und Docker Compose, ideal für Analysen, Web-Tracking und Datenanalyse.

## 👋 About Me | Über mich

I am Rodrigo Teixeira, a Web Content Manager with a passion for data-driven decision-making, web analytics, and digital marketing. This project reflects my hands-on experience with web analytics platforms and containerization, demonstrating my technical skills in setting up environments that prioritize data privacy and user autonomy. I am excited about opportunities that allow me to contribute to web development and analytics, and I look forward to bringing my expertise to your team.

Ich bin Rodrigo Teixeira, ein Web Content Manager mit einer Leidenschaft für datengetriebene Entscheidungsfindung, Web-Analyse und digitales Marketing. Dieses Projekt spiegelt meine praktische Erfahrung mit Web-Analyse-Plattformen und Containerisierung wider und demonstriert meine technischen Fähigkeiten bei der Einrichtung von Umgebungen, die den Datenschutz und die Autonomie der Nutzer in den Vordergrund stellen. Ich freue mich auf Möglichkeiten, zu Webentwicklung und Analyse beizutragen, und darauf, meine Expertise in Ihr Team einzubringen.

## 📄 Overview | Überblick

Matomo is an open-source web analytics platform, similar to Google Analytics, but with a strong emphasis on data privacy and full data ownership. This setup is intended for local development and testing purposes, allowing quick deployment of Matomo on any machine using Docker.

Matomo ist eine Open-Source-Webanalyseplattform, ähnlich wie Google Analytics, jedoch mit starkem Fokus auf Datenschutz und vollständigem Besitz der Daten. Diese Einrichtung ist für die lokale Entwicklung und Testzwecke gedacht und ermöglicht eine schnelle Bereitstellung von Matomo auf jeder Maschine mit Docker.

## 🚀 Setup Instructions | Installationsanleitung

Follow the steps below to set up and run Matomo on your local machine using Docker:

Folgen Sie den untenstehenden Schritten, um Matomo auf Ihrem lokalen Rechner mit Docker einzurichten und auszuführen:

### 1️⃣ Clone the Repository | Klonen Sie das Repository

Clone this repository to your local machine:

Klonen Sie dieses Repository auf Ihren lokalen Rechner:

```bash
git clone https://github.com/yourusername/matomo-docker-setup.git
cd matomo-docker-setup
```

### 2️⃣ Start Matomo | Starten Sie Matomo

Use Docker Compose to start the Matomo and MariaDB containers:

Verwenden Sie Docker Compose, um die Matomo- und MariaDB-Container zu starten:

```bash
docker-compose up -d
```

### 3️⃣ Access Matomo | Zugriff auf Matomo

Open your web browser and go to:

Öffnen Sie Ihren Webbrowser und gehen Sie zu:

```bash
http://localhost:8080
```

### 4️⃣ Follow the on-screen instructions to complete the setup | Folgen Sie den Anweisungen auf dem Bildschirm, um die Einrichtung abzuschließen:

- **Database Server:** `mariadb`
- **Database Name:** `matomo`
- **User:** `matomo`
- **Password:** `matomo_secret`

Create a superuser account with your preferred credentials to access the Matomo dashboard.

Erstellen Sie ein Superuser-Konto mit Ihren bevorzugten Zugangsdaten, um auf das Matomo-Dashboard zuzugreifen.

## ⚙️ Docker Configuration | Docker-Konfiguration

The `docker-compose.yml` file contains the configuration for the Matomo and MariaDB services:

Die Datei `docker-compose.yml` enthält die Konfiguration für die Matomo- und MariaDB-Dienste:

```yaml
version: '3.7'

services:
  matomo:
    image: matomo:latest
    ports:
      - "8080:80"
    volumes:
      - ./matomo:/var/www/html
    environment:
      - MATOMO_DATABASE_HOST=mariadb
      - MATOMO_DATABASE_ADAPTER=mysqli
      - MATOMO_DATABASE_TABLES_PREFIX=matomo_
      - MATOMO_DATABASE_DBNAME=${MYSQL_DATABASE}
      - MATOMO_DATABASE_USERNAME=${MYSQL_USER}
      - MATOMO_DATABASE_PASSWORD=${MYSQL_PASSWORD}
      - MATOMO_SUPERUSER_NAME=${MATOMO_SUPERUSER_NAME}
      - MATOMO_SUPERUSER_PASSWORD=${MATOMO_SUPERUSER_PASSWORD}
      - MATOMO_SUPERUSER_EMAIL=${MATOMO_SUPERUSER_EMAIL}

  mariadb:
    image: mariadb:latest
    environment:
      - MYSQL_ROOT_PASSWORD=${MYSQL_ROOT_PASSWORD}
      - MYSQL_DATABASE=${MYSQL_DATABASE}
      - MYSQL_USER=${MYSQL_USER}
      - MYSQL_PASSWORD=${MYSQL_PASSWORD}
    volumes:
      - ./mariadb:/var/lib/mysql
```

## 🛠️ Relevant Skills Demonstrated | Relevante Fähigkeiten demonstriert

- **Web Analytics Expertise:** Proficient in setting up and configuring Matomo, showcasing skills in data analysis and web tracking.
- **Web-Analyse-Expertise:** Erfahrung in der Einrichtung und Konfiguration von Matomo, zeigt Fähigkeiten in der Datenanalyse und im Web-Tracking.
- **Docker and DevOps:** Experience in using Docker for efficient deployment and management of web applications, demonstrating knowledge of modern DevOps practices.
- **Docker und DevOps:** Erfahrung im Einsatz von Docker für die effiziente Bereitstellung und Verwaltung von Webanwendungen, zeigt Kenntnisse moderner DevOps-Praktiken.
- **Data Privacy Focus:** Strong understanding of data privacy, with experience in using Matomo to provide analytics solutions that respect user privacy.
- **Fokus auf Datenschutz:** Starkes Verständnis für Datenschutz, mit Erfahrung in der Nutzung von Matomo zur Bereitstellung von Analyse-Lösungen, die die Privatsphäre der Nutzer respektieren.

## 🎯 Project Impact | Projektwirkung

This setup provides a secure, flexible, and scalable web analytics solution that allows companies to gain valuable insights into their user behavior while maintaining full control over their data.

Diese Einrichtung bietet eine sichere, flexible und skalierbare Web-Analyse-Lösung, die es Unternehmen ermöglicht, wertvolle Einblicke in das Nutzerverhalten zu gewinnen und gleichzeitig die volle Kontrolle über ihre Daten zu behalten.

## 📞 Let's Connect | Kontaktieren Sie mich

I am enthusiastic about bringing my skills and passion for web analytics to your team. If you are looking for someone who combines technical expertise with a strong commitment to data privacy and user experience, let’s chat! Feel free to explore this project further, and don't hesitate to contact me on [LinkedIn](https://www.linkedin.com/in/rodrigo-teixeira-b8b889302/) or via email.

Ich bin begeistert davon, meine Fähigkeiten und meine Leidenschaft für Web-Analyse in Ihr Team einzubringen. Wenn Sie jemanden suchen, der technisches Fachwissen mit einem starken Engagement für Datenschutz und Benutzererfahrung kombiniert, lassen Sie uns reden! Zögern Sie nicht, dieses Projekt weiter zu erkunden und mich auf [LinkedIn](https://www.linkedin.com/in/rodrigo-teixeira-b8b889302/) oder per E-Mail zu kontaktieren.

## 🏆 Personal Reflections & Achievements | Persönliche Reflexionen & Erfolge

Through my work with Matomo and other web analytics platforms, I have developed a strong appreciation for the importance of data privacy and ethical data practices. I believe in using technology to empower organizations while respecting user rights, which is why I focus on open-source solutions like Matomo that prioritize data ownership and transparency.

During my career, I have consistently demonstrated a commitment to ethical web analytics, ensuring that data-driven decisions are made with respect for user privacy. My approach combines technical expertise with a dedication to implementing best practices in data security and compliance, making me a reliable advocate for responsible analytics.

Durch meine Arbeit mit Matomo und anderen Webanalyseplattformen habe ich eine große Wertschätzung für die Bedeutung von Datenschutz und ethischen Datenpraktiken entwickelt. Ich glaube daran, dass Technologie Organisationen stärkt und gleichzeitig die Rechte der Nutzer respektiert. Deshalb konzentriere ich mich auf Open-Source-Lösungen wie Matomo, die den Datenbesitz und die Transparenz in den Vordergrund stellen.

In meiner Karriere habe ich stets mein Engagement für eine ethische Web-Analyse unter Beweis gestellt, indem ich sichergestellt habe, dass datenbasierte Entscheidungen mit Respekt für die Privatsphäre der Nutzer getroffen werden. Mein Ansatz kombiniert technisches Fachwissen mit der Verpflichtung, Best Practices in der Datensicherheit und Compliance umzusetzen, was mich zu einem zuverlässigen Fürsprecher für verantwortungsvolle Analysen macht.

---

*Thank you for reviewing my work! | Danke, dass Sie meine Arbeit geprüft haben!*
