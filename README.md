# ThingsBoard Configuration Repository

Dieses Repository enthält die ThingsBoard-Konfiguration und Entitäten für die IoT-Anwendung.

## 📋 Repository-Zweck

Dieses Repository speichert ThingsBoard-Entitäten (Devices, Assets, Dashboards, Rule Chains, etc.) in strukturierter Form und ist für die **Version Control Integration** in ThingsBoard optimiert.

## 🏗️ Repository-Struktur

Das Repository folgt der ThingsBoard-Standardstruktur mit Ordnern für jede Entity-Art:

```
├── asset/                      # IoT Assets (virtuelle Entitäten)
├── asset_profile/              # Asset Profile (benutzerdefiniert)
├── customer/                   # Customer-Definitionen
├── dashboard/                  # Dashboards
├── device/                     # Geräte (IoT Devices)
├── device_profile/             # Device Profile (benutzerdefiniert)
├── groups/                     # Gruppen-Definitionen
├── hierarchy/                  # Entitätshierarchien
├── notification_rule/          # Benachrichtigungsregeln
├── notification_target/        # Benachrichtigungsziele
├── notification_template/      # Benachrichtigungsvorlagen
├── report_template/            # Report-Vorlagen
├── role/                       # Benutzerrollen
├── rule_chain/                 # Rule Chains (Business Logic)
├── scheduler_event/            # Scheduler-Events
├── tb_resource/                # Ressourcen (Bilder, Skripte)
└── _excluded_from_import/      # Ausgeschlossene Dateien (siehe unten)
```

## 🔄 Import in ThingsBoard (Version Control)

### Voraussetzungen
- ThingsBoard Instanz (CE oder PE)
- Git-Integration aktiviert
- Zugriff auf die ThingsBoard-Verwaltungsoberfläche

### Import-Schritte

1. **In ThingsBoard anmelden**
   - Navigiere zu: **Settings** → **Repository** (oder **Version Control**)

2. **Repository verbinden**
   - Klicke auf **"Add repository"** oder **"Restore from Git"**
   - Wähle diese GitHub-Repository aus
   - Wähle Branch: `main` (oder `thingsboard-cleanup` für die neueste bereinigte Version)

3. **Konfiguration überprüfen**
   - Stelle sicher, dass die Entitäten korrekt erkannt werden
   - Prüfe auf Konflikte mit existierenden Entities

4. **Import starten**
   - Klicke auf **"Import"** oder **"Restore"**
   - Warte auf die Bestätigung
   - Überprüfe die Logs auf Fehler

### Nach dem Import
- Die Dashboards sollten unter **Dashboards** sichtbar sein
- Die Devices sollten unter **Devices** auftauchen
- Rule Chains sollten aktiv sein und Daten verarbeiten
- Überprüfe die **Rule Chain** Logs für potenzielle Fehler

---

## ⚠️ Ausgeschlossene Dateien

Einige Dateien wurden aus dem Import ausgeschlossen. Weitere Informationen findest du in:
📄 **[`_excluded_from_import/README.md`](_excluded_from_import/README.md)**

### Zusammenfassung der ausgeschlossenen Dateien:
- ❌ `device_profile/b9f0be30-52d5-11f1-bdfb-2fcbd7265065.json` (Default Device Profile)
- ❌ `asset_profile/b9f1a890-52d5-11f1-bdfb-2fcbd7265065.json` (Default Asset Profile)

**Grund**: Diese sind System-Profile und würde Konflikte in bestehenden ThingsBoard-Instanzen verursachen.

---

## ✅ Validierung

Das Repository wurde bereinigt und validiert:

- ✅ Alle JSON-Dateien sind syntaktisch korrekt
- ✅ Keine beschädigten oder unvollständigen Dateien
- ✅ Alle Entitäts-IDs sind eindeutig
- ✅ Struktur entspricht ThingsBoard Version Control Standard
- ✅ Projektbezogene Objekte (Devices, Dashboards, Rule Chains) sind vollständig erhalten

---

## 📝 Inhalt des Repositories

### Wichtige Entitäten

| Entity-Typ | Anzahl | Beschreibung |
|-----------|--------|----------|
| **Devices** | 1 | IoT-Geräte/Sensoren |
| **Device Profiles** | 4 | Geräte-Konfigurationsprofile (benutzerdefiniert) |
| **Assets** | 1 | Virtuelle Assets (z.B. Booking-System) |
| **Asset Profiles** | 2 | Asset-Konfigurationsprofile (benutzerdefiniert) |
| **Dashboards** | 3 | Visualisierungs-Dashboards |
| **Rule Chains** | 2 | Datenverarbeitungs- und Business-Logic-Chains |

---

## 🚀 Nächste Schritte

1. **Import durchführen** gemäß der Anleitung oben
2. **Dashboards überprüfen** → Sollten Daten anzeigen
3. **Rule Chains testen** → Müssen Daten korrekt verarbeiten
4. **Geräte kalibrieren** → Devices sollten Verbindung zur ThingsBoard-Instanz haben

---

## 🔧 Bekannte Probleme & Lösungen

### Problem: Import schlägt fehl
- **Grund**: Duplikte in der Instanz
- **Lösung**: Alte Versionen löschen oder Import zu neuem Workspace durchführen

### Problem: Dashboards zeigen keine Daten
- **Grund**: Devices sind nicht verbunden oder senden keine Daten
- **Lösung**: Geräte überprüfen → Credentials validieren → Verbindung testen

### Problem: Rule Chains funktionieren nicht
- **Grund**: Abhängigkeiten nicht erfüllt oder Fehlkonfiguration
- **Lösung**: Rule Chain Logs überprüfen, Abhängigkeiten validieren

---

## 📞 Support

Bei Fragen oder Problemen:
1. Überprüfe die ThingsBoard-Dokumentation: https://thingsboard.io/docs/
2. Kontrolliere die Logs in der ThingsBoard-Instanz
3. Validiere die JSON-Dateien auf Fehler

---

**Zuletzt aktualisiert**: 2026-06-16  
**Repository Status**: ✅ Bereit für ThingsBoard Version Control Import