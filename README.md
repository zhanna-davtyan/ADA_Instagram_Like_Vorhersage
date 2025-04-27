# Projekt: Instagram Like-Vorhersage mittels Bildanalyse (ADA)

Dieses Repository enthält das Gruppenprojekt für das Modul "Angewandte Daten-Analyse (ADA)". Ziel des Projekts ist die Entwicklung eines Modells zur Vorhersage des Engagements (speziell der Like-Anzahl) von Instagram-Posts basierend auf visuellen Merkmalen der Bilder und zugehörigen Metadaten.

## Team

* Zhanna Davtyan
* Laura Remmert
* Quentin Alpmann


## Zielsetzung

Im Social Media Marketing ist die Vorhersage des potenziellen Erfolgs von Inhalten eine Herausforderung. Dieses Projekt zielt darauf ab:

1.  Einen Datensatz von Instagram-Posts (Bilder + Metadaten inkl. Likes) zu analysieren.
2.  Relevante visuelle Merkmale (Farben, Helligkeit, Objekte etc.) und Metadaten-Features zu extrahieren.
3.  Ein Machine-Learning-Modell zu entwickeln, das die Like-Anzahl basierend auf diesen Merkmalen prognostiziert.
4.  Die Ergebnisse zu evaluieren und zu interpretieren, insbesondere den Einfluss visueller Faktoren (z.B. mittels Farb-Analyse / "Heatmap").

## Datensatz

* **Quelle:** Kaggle
* **Name:** Instagram posts dataset
* **ID:** `thecoderenroute/instagram-posts-dataset`
* **Link:** [https://www.kaggle.com/datasets/thecoderenroute/instagram-posts-dataset](https://www.kaggle.com/datasets/thecoderenroute/instagram-posts-dataset)
* **Inhalt:** Über 5.000 Bilder aus ca. 2.000 Posts, jeweils mit zugehörigen Metadaten (Likes, Kommentare, Zeitstempel etc.) im JSON-Format und Bildunterschriften als Textdatei.
* **Größe:** ca. 1.82 GB

*Hinweis:* Der Datensatz wird **nicht** direkt mit diesem Repository ausgeliefert, sondern bei Bedarf automatisch heruntergeladen (siehe Abschnitt Datenbeschaffung).

## Setup-Anleitung

Um das Projekt lokal auszuführen, folgen Sie bitte diesen Schritten:

1.  **Repository klonen:**
    ```bash
    git clone https://github.com/zhanna-davtyan/ADA_Instagram_Like_Vorhersage.git
    cd ADA_Instagram_Like_Vorhersage
    ```
2.  **Python-Version sicherstellen:** 
    * Dieses Projekt wurde mit Python `3.10.x` entwickelt. 

3.  **Virtuelle Umgebung erstellen:**
    ```bash
    python -m venv .venv
    ```
    *(Oder `python3` statt `python`, je nach Systemkonfiguration)*
4.  **Umgebung aktivieren:**
    * macOS/Linux: `source .venv/bin/activate`
    * Windows: `.\.venv\Scripts\activate`
5.  **Bibliotheken installieren:** Alle benötigten Pakete sind in `requirements.txt` aufgelistet.
    ```bash
    pip install -r requirements.txt
    ```
6.  **Kaggle API Key einrichten:** Für den automatischen Datendownload ist ein Kaggle API Key **erforderlich**.
    * Laden Sie Ihre `kaggle.json`-Datei von Ihrem Kaggle-Account herunter ([Anleitung](https://www.kaggle.com/docs/api#authentication)).
    * Erstellen Sie den Ordner `~/.kaggle/` (falls nicht vorhanden).
    * Platzieren Sie die `kaggle.json`-Datei in diesem Ordner. Stellen Sie sicher, dass die Berechtigungen korrekt gesetzt sind (oft `chmod 600 ~/.kaggle/kaggle.json`).

## Datenbeschaffung

* Der benötigte Kaggle-Datensatz (ca. 1.82 GB) ist **nicht** Teil dieses Git-Repositories.
* Das erste Jupyter Notebook (z.B. `notebooks/01_Daten_Laden_Exploration.ipynb`) enthält am Anfang Code-Zellen, die **automatisch prüfen**, ob der Datensatz im Verzeichnis `daten/rohdaten/instagram-posts-dataset/` vorhanden ist.
* **Falls die Daten fehlen:** Der Code versucht, den Datensatz über `kaggle` herunterzuladen und in den Zielordner zu kopieren. Hierfür ist der eingerichtete Kaggle API Key notwendig.
* Dieser Vorgang stellt sicher, dass Sie den Datensatz nicht manuell herunterladen müssen, die Daten aber für die Ausführung lokal verfügbar sind.

