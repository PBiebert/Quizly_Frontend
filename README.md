# Quizly Frontend

![Quizly Logo](/assets/icons/logoheader.png)

Quizly ist das Frontend für eine KI-gestützte Quiz-Plattform. Das Backend wird separat mit Django umgesetzt und generiert aus YouTube-Videos automatisch Multiple-Choice-Quizze. Ziel des Projekts ist es, Frontend und Backend sauber zu verbinden, damit die Plattform vollständig funktioniert.

## Voraussetzungen

- Ein laufendes Django-Backend für Quizly, das die API bereitstellt.
- Das Backend muss JWT-Authentifizierung über HttpOnly-Cookies unterstützen: Der Access-Token wird beim Login als HttpOnly-Cookie gesetzt, Requests an geschützte Routen laufen darüber. Das Frontend hat keinen direkten Zugriff auf den Token (kein localStorage, kein Authorization-Header). CORS muss serverseitig für das lokale Frontend erlaubt sein.
- Visual Studio Code mit der Live-Server-Erweiterung oder eine ähnliche Möglichkeit, die index.html lokal im Browser zu starten.

## Schnellstart

1. Stelle sicher, dass das Backend läuft (Standard: http://127.0.0.1:8000).
2. Öffne dieses Frontend-Projekt in Visual Studio Code.
3. Starte die oberste index.html mit Live Server.
4. Registriere dich oder melde dich mit einem bestehenden Account an.

## Ziel des Projekts

Dieses Frontend wurde bewusst mit Vanilla JavaScript erstellt, damit die Integration mit dem Django-Backend möglichst direkt und nachvollziehbar bleibt.

- **Registrierung und Login**: Nutzer können sich registrieren und anmelden, Authentifizierung erfolgt über JWT in HttpOnly-Cookies.
- **Quiz-Generierung**: Aus einer YouTube-URL wird über das Backend automatisch ein Quiz erstellt.
- **Quiz-Durchführung**: Interaktive Beantwortung von Multiple-Choice-Fragen mit direkter Auswertung.
- **Ergebnisübersicht**: Anzeige der Quiz-Ergebnisse mit richtigen und falschen Antworten.
- **Quiz-Verwaltung**: Eigene Quizze in einer Bibliothek ansehen, bearbeiten und löschen.
- **Einfacher Einstieg**: Ohne Frameworks bleibt der Code leicht lesbar und schnell anpassbar.

## Features

| Bereich | Funktion |
|---|---|
| Auth | Login, Registrierung, Logout, JWT-Authentifizierung über HttpOnly-Cookies |
| Quiz-Generierung | Erstellung eines Quiz aus einer YouTube-URL |
| Bibliothek | Übersicht aller eigenen Quizze mit Bearbeiten- und Löschen-Funktion |
| Quiz-Durchführung | Beantwortung von Multiple-Choice-Fragen mit Fortschrittsanzeige |
| Ergebnisse | Auswertung mit richtigen/falschen Antworten je Frage |

## API-Anbindung

Die API-URLs sind in `shared/js/config.js` definiert. Dort sind unter anderem die Endpunkte für Login, Registrierung, Logout, Token-Refresh und Quiz-Erstellung/-Abruf hinterlegt.

Die Authentifizierung erfolgt über JWT, das als HttpOnly-Cookie vom Backend gesetzt wird. Das Frontend sendet Requests mit Credentials, hat aber keinen direkten Zugriff auf den Token selbst.

## Architektur & Konventionen

- **Kein Build-Step** – die Dateien werden direkt vom Browser geladen.
- **Shared JS/CSS** – wiederverwendbare Module liegen in `shared/`.
- **Template-Funktionen** – HTML-Strukturen werden per JavaScript erzeugt.
- **Cookie-basiert** – kein Token-Handling im Frontend-Code, Authentifizierung läuft vollständig über HttpOnly-Cookies.

## Hinweis

Dieses Projekt ist ausschliesslich für Schüler der Developer Akademie gedacht und nicht zur freien Nutzung oder Weitergabe freigegeben.
