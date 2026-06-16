# Ausgeschlossene Dateien aus dem Import

Diese Dateien wurden aus dem ThingsBoard-Import ausgeschlossen, da sie Konflikte mit bestehenden ThingsBoard-Instanzen verursachen würden.

## Default-Profile (Systemprofile)

### 1. `device_profile/b9f0be30-52d5-11f1-bdfb-2fcbd7265065.json`
- **Grund**: Default Device Profile (`"default": true`)
- **Beschreibung**: Dies ist das Standard-Device-Profil von ThingsBoard
- **Problem**: Beim Import in eine bestehende ThingsBoard-Instanz würde dies versuchen, das existierende System-Profil zu überschreiben
- **Status**: ⚠️ Ausgeschlossen

### 2. `asset_profile/b9f1a890-52d5-11f1-bdfb-2fcbd7265065.json`
- **Grund**: Default Asset Profile (`"default": true`)
- **Beschreibung**: Dies ist das Standard-Asset-Profil von ThingsBoard
- **Problem**: Beim Import in eine bestehende ThingsBoard-Instanz würde dies versuchen, das existierende System-Profil zu überschreiben
- **Status**: ⚠️ Ausgeschlossen

## Behobene Fehler

### `device/ad6e02f0-5dc3-11f1-9511-2580300f449d.json`
- **Problem**: Doppeltes `"type"` Field in `deviceData.configuration` (Zeilen 15-16)
- **Fix**: Duplikat entfernt, nur ein `"type": "DEFAULT"` behalten
- **Status**: ✅ Repariert und importierbar

## Import-Richtlinien

Wenn du diese ausgeschlossenen Dateien importieren möchtest, solltest du:

1. **Default-Profile NICHT importieren** - diese sollten von deiner ThingsBoard-Instanz stammen
2. **Nur benutzerdefinierte Profile importieren** - diese befinden sich außerhalb von `_excluded_from_import/`

## Repository für Version Control vorbereitet

Das Repository ist nun für ThingsBoard Version Control optimiert und kann direkt importiert werden.