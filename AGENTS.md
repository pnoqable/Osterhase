# AGENTS.md

## Projektueberblick
- Dieses Repository ist ein kleines, statisches Browser-Spiel ohne Build-System.
- Die Anwendung lebt komplett in `index.html`.
- `LICENSE` enthaelt eine MIT-Lizenz.

## Struktur
- `index.html` enthaelt HTML-Markup, Inline-CSS und die komplette JavaScript-Spiel-Logik.
- Es gibt aktuell keine externen Assets, keine Abhaengigkeiten und keinen Paketmanager.
- Das Spiel rendert auf ein `canvas`-Element und nutzt DOM-Elemente nur fuer Titel, Hinweise und Einstellungs-UI.

## Arbeitsregeln
- Aendere nur das, was fuer die angeforderte Aufgabe notwendig ist.
- Behalte den Single-file-Ansatz bei, solange nicht ausdruecklich eine Umstrukturierung verlangt wird.
- Verwende fuer neue Texte und Kommentare bevorzugt Deutsch, weil die sichtbare UI deutschsprachig ist.
- Fuehre neue Logik moeglichst in klar abgegrenzten Abschnitten ein, statt bestehende Zeichen- und Updatepfade unnoetig zu vermischen.
- Vermeide unnoetige Inline-Event-Handler-Ausweitung; bestehende Muster duerfen fuer kleine Erweiterungen beibehalten werden, groessere Interaktionen sollten ueber `addEventListener` laufen.

## Technische Hinweise
- Die Szene verwendet einen deterministischen Zufallsgenerator mit festem Seed fuer reproduzierbare Platzierung von Blumen, Eiern und Effekten.
- Persistente Einstellungen laufen ueber `localStorage` mit den Schluesseln `exp_enabled` und `exp_strength`.
- Die Spielschleife basiert auf `requestAnimationFrame` und normiert Bewegungen auf ca. 60 FPS.
- Das Rendering ist zustandsbasiert; bei Canvas-Aenderungen immer auf saubere `save()`/`restore()`-Paare achten.

## Validierung
- Nach Aenderungen `index.html` direkt im Browser oeffnen.
- Pruefen:
  - Canvas rendert ohne Konsolenfehler.
  - Bewegung per Pfeiltasten und `WASD` funktioniert.
  - Leertaste loest den Looping-Sprung aus.
  - Eier koennen eingesammelt werden.
  - Explosionseinstellungen bleiben nach Reload erhalten.
  - Gewinnzustand und Feuerwerk funktionieren weiterhin.

## Nicht annehmen
- Keine Build-, Test- oder Lint-Infrastruktur voraussetzen.
- Keine Frameworks oder Module einfuehren, sofern das nicht explizit verlangt wird.
