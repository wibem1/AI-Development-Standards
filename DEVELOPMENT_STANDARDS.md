# Gemeinsame Standards für KI-gestützte Softwareentwicklung
Version 1.1 — 16. November 2026

**Geltung:** Für alle bestehenden und zukünftigen Softwareprojekte des Projektinhabers, unabhängig vom KI-Modell und davon, ob Chat, Work, Codex, Claude oder Gemini eingesetzt wird. Projektspezifische Regeln ergänzen diese Standards; ausdrückliche aktuelle Benutzeranweisungen gehen vor.

## Leitprinzip
**Ein überschaubarer Entwicklungsschritt → ein objektiv überprüfbares Ergebnis → gesicherter Projektstand → nächster Schritt.**

## Projektgedächtnis
1. GitHub ist die dauerhafte, gemeinsame Quelle für Quellcode und Entwicklungsstand. Ein einzelner Chatverlauf ist keine verlässliche Projektakte.
2. Jedes Projekt führt eine kurze `PROJECT_STATE.md`: Ziel, aktueller Quellstand/Version, **nachgewiesene** Funktionen mit Prüfgrundlage, offene Fehler/Blocker, nächster einzelner Schritt. Eine vorhandene TODO-Datei darf ergänzend weitergenutzt werden.
3. Jedes Projekt besitzt eine kurze `AGENTS.md` oder gleichwertige Einstiegshinweise mit Link auf diese zentralen Standards. Die KI muss die Regeln zu Beginn ausdrücklich lesen; ein Link allein garantiert nicht die automatische Berücksichtigung.
4. Nach einem **abgeschlossenen relevanten** Entwicklungsschritt werden Code, Testergebnisse und Projektstand gemeinsam gesichert. Bei Diskussionsschritten nur dokumentieren, wenn eine neue verbindliche Entscheidung getroffen wurde. Keine unnötige ZIP-Verwaltung oder Protokollflut.

## Qualitätsdisziplin
5. Streng unterscheiden: **geplant / implementiert / statisch geprüft / mit Simulation getestet / mit realen Komponenten getestet / vom Nutzer bestätigt**. Keine Freigabe aus bloßen Build-Erfolgen oder unüberprüften Behauptungen ableiten.
6. Der letzte verifizierte Stand bleibt reproduzierbar erhalten. Problematische Experimente dürfen ihn nicht überschreiben.
7. Kleine, isolierte Tests vor Integration und Verpackung. Insbesondere bei grafischen Programmen muss das Ergebnis in der echten Engine / Anwendung geprüft werden, bevor eine vollständige App als funktionsfähig gilt.
8. Nach zwei erfolglosen gezielten Korrekturversuchen zuerst Ursache eingrenzen, Belege prüfen und Vorgehen überdenken; keine unkontrollierten Wiederholungen.
9. Keine gleichzeitigen Änderungen verschiedener KI-Agenten an demselben unkoordinierten Quellstand.

## Ressourcen und Werkzeuge
10. Normale Chats und einfache lokale Tests bevorzugen, wenn sie ausreichen. Work nur für klar umrissene Aufgaben mit erkennbarem Mehrwert.
11. GitHub Actions und native Builds nur bei sachlicher Notwendigkeit, möglichst manuell und ohne Retry-Schleifen. GitHub als Gedächtnis benötigt keine dauernden Builds.
12. Kostenpflichtige API-Aufrufe nur, wenn sie für einen konkreten Test erforderlich und preislich vertretbar sind. Ein Prompt-Budget ist **keine** technische Kostengarantie.
13. Keine neue Versionsnummer oder Download-Freigabe, bevor die dafür erforderlichen Prüfungen tatsächlich erfolgreich abgeschlossen sind.

## Sitzungswechsel
14. Ein neuer Chat/Agent liest zuerst die globalen Regeln, die projektspezifischen Regeln, `PROJECT_STATE.md` und den relevanten Code. Er benennt knapp, was belegt ist, was fehlt und welche Aufgabe ansteht.
15. Ein Abbruch kann ungesicherte Arbeit verlieren lassen. Es gilt der zuletzt tatsächlich auf GitHub gesicherte Stand. Wiederherstellung ohne Chatgedächtnis muss möglich sein.
16. Die Regeln gelten **projektübergreifend**. VectorCraft ist nur das erste Testprojekt, nicht der Geltungsbereich der Methode.


## Dynamische KI-Modellauswahl (verbindlich ab 16.11.2026)
17. **Alle KI-fähigen Apps** sollen, sofern die jeweilige Provider-API dies ermöglicht, eine dynamische Modellliste statt fest verdrahteter Modellnamen anbieten. Neue Modelle dürfen nicht routinemäßig ein App-Update erfordern. Neue Apps berücksichtigen dies von Beginn an; bestehende Apps erhalten es nur, soweit noch nicht funktionierend vorhanden. Keine Umgestaltung funktionierender Modellauswahlen ohne konkreten Grund.
18. Anbieterunabhängige Oberfläche: verfügbare Anbieter, aktuelle Modell-ID und Anzeigename, manuelle Aktualisierung, zuletzt gewählte Konfiguration; fehlende oder zurückgezogene Modelle nachvollziehbar kennzeichnen. Ein gespeichertes Modell ist **kein** Beleg aktueller Verfügbarkeit: vor kostenpflichtigen Aufrufen beim Anbieter nachprüfen.
19. **Modellverfügbarkeit ist nicht Kompatibilität.** Nur passende Text-/Ausgabe-Modalitäten anzeigen; aufgabenspezifische Antwortformate, strukturierte Ausgabe, Werkzeugaufrufe und Kontext-/Ausgabelimits vor Nutzung prüfen. Fehlende Metadaten nicht erraten; bei Unsicherheit warnen, erforderlichenfalls Freigabe und gezielte kostenfreie/ausdrücklich genehmigte Tests verlangen. Modellnamen, Preise oder API-Parameter nicht aus Versionsbezeichnungen ableiten.
20. Denksteuerung, Ausgabebegrenzung und besondere Parameter ausschließlich nach gemeldeten/validierten Fähigkeiten anbieten; nicht unterstützte Parameter niemals blind mitsenden. Providerwechsel darf bestehende Profile, Schlüssel oder Nutzerdaten nicht zerstören. Fehlerfälle: Netzwerkausfall, Rate-Limit, entzogenes Modell, unvollständiger Katalog, falscher Schlüssel, nicht unterstützte Parameter. Diagnose ohne Geheimnisse.
21. Schlüssel getrennt je Anbieter und nach Plattform sicher verwalten, nie einchecken oder in Diagnose exportieren. API-Aufrufe nur bewusst vom Benutzer ausgelöst, ohne automatischen kostenpflichtigen Modellvergleich; gegebenenfalls nachvollziehbare Kostenschätzung aus frischen Anbieterangaben. Offlinefunktionen unverändert erhalten.
22. **Wiederverwendbares Muster, keine zentrale Laufzeitpflicht:** Gemeinsam dokumentierte Schnittstelle/Konformitätstests, aber jede App muss eigenständig start- und benutzbar bleiben. OpusCraft dient als mögliche Referenz, ist aber keine ungeprüft übertragbare Bibliothek. Bei Umsetzung pro App projektbezogene Tests, neue Versionsnummer gemäß Nutzerwunsch, GitHub-Projektstand aktualisieren und Veröffentlichung erst nach nachgewiesenen Prüfungen. Reine Regel-/Planungsänderungen sind keine App-Releases.

## Ursprung und Nachweis
Erarbeitet am 23.10.2026 aus der Analyse der VectorCraft-Entwicklung und einer dokumentierten Chat-zu-Chat-Übernahmeprüfung. Der erste Übernahmetest zeigte, dass ein neuer Chat Projektinformationen über GitHub sinnvoll rekonstruieren konnte. Ein allgemeiner Beweis für fehlerfreie Übergaben oder autonome Entwicklung ist das **nicht**.
