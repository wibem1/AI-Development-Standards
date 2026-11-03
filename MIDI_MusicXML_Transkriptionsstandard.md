# Verbindlicher Standard: MIDI → lesbare, klangnahe MusicXML-Klavierpartitur

Version 1.0 — 2026-11-03

## Ziel
Eine musikalisch plausible, aufführbare und gut lesbare zweihändige Klavierpartitur rekonstruieren, deren klangliche Wirkung dem expressiv gespielten Original-MIDI möglichst nahekommt. Weder reine MIDI-Event-Abschrift noch kosmetisch vereinfachte, klanglich verfälschte Notation sind akzeptabel.

## Grundsätze
1. **Original bleibt Referenz.** MIDI-Notenanfänge, Tonhöhen, Notenenden, Anschlagstärken, Tempoverlauf und gegebenenfalls Pedal/Controller unverändert archivieren. Niemals die einzige Originaldatei überschreiben.
2. **MIDI ist eine Aufführung, keine Partitur.** Kleine Asynchronitäten können Ausdruck, Vorschläge oder Arpeggierungen sein; nicht pauschal als Fehler behandeln.
3. **Rhythmus rekonstruieren.** Taktweise Puls, Metrum, Unterteilungen, Triolen und Phrasen identifizieren. Quantisierung nur mit musikalischer Begründung und kontextbezogener Toleranz.
4. **Stimmen musikalisch trennen.** Melodie, Bass, Begleitung und Mittelstimmen nach Phrasen, Kontinuität, Tonlage, Bewegung und Funktion zuordnen. Nicht nur nach Tonhöhe oder zeitlicher Überlappung.
5. **Handverteilung begründen.** Klaviersatz auf zwei Systeme verteilen, auch Überkreuzungen zulassen, ohne musikalische Stimmen zu zerreißen. Spielbarkeit und Ergonomie kontrollieren.
6. **Notation lesbar halten.** Einfache Notenwerte, Bögen, Haltebögen, Vorschlagsnoten, Arpeggiozeichen und gezielte Mehrstimmigkeit verwenden. Keine künstlichen Pausen, stimmlose Lücken oder Hilfslinien-Exzesse als Nebenprodukt des Algorithmus.
7. **Klingende Dauer schützen.** Niemals Akkordtöne pauschal bis zum nächsten Anschlag verlängern; nie alle Stimmen auf eine Dauer zwingen. Notierte Dauer und reale Artikulation unterscheiden; erforderlichenfalls Playback-Informationen ergänzen oder klangtreues Original-MIDI getrennt behalten.
8. **Reduktion ist kein Selbstzweck.** Auch einfache und ostinate Figuren können bewusstes Stilmittel sein. Nicht nach vermeintlicher Komplexität urteilen.

## Verpflichtender Arbeitsablauf
A. Original-MIDI inventarisieren: Tracks/Kanäle, PPQ, Meter, Tempo, Controller, Note-on/off, Polyphonie, Dauern, Register, Form und Taktgrenzen.
B. 1–4 repräsentative Takte auswählen, insbesondere schwierige Stellen: Akkordwiederholung, überlappende Stimmen, ungleich lange Töne, Triolen, Vorschläge.
C. Diese Takte musikalisch analysieren; konkrete Notierung entscheiden. Mehrdeutigkeiten dokumentieren.
D. Test-MusicXML erzeugen und **wirklich rendern** (nach Möglichkeit MuseScore-kompatibel) und visuell auf Haltebögen, Stimmen, Pausen, Schlüssel, Akkorde, Taktstriche und Hilfslinien prüfen.
E. Klangvergleich: MusicXML nach MIDI zurückexportieren; Original und Rückexport mit identischem Instrument/Tempo abgleichen. Tonhöhen, Anschläge, rhythmische Einsätze, Dauern, Akkorddichte, Polyphonie und Phrasen vergleichen; expressive Abweichungen nachvollziehbar dokumentieren.
F. Erst nach erfolgreicher Testpassage die vollständige Partitur aufbauen; erneut alle Takte und kritische Stellen einzeln kontrollieren.
G. Nicht als fertig oder klanggleich ausgeben, wenn Hör- oder Renderprüfung fehlt. Einschränkungen offen benennen.

## Explizit verbotene Abkürzungen
- Pauschales Runden sämtlicher MIDI-Dauern ohne Kontext.
- Verlängern von Akkordtönen bis zum jeweils nächsten Note-on.
- Ausschließliche Stimmenzuweisung nach Überlappung oder starrer Tonhöhenschwelle.
- Vollständige 50+-Takte-Ausgabe ohne geprüfte Testpassage.
- Gleichsetzung von rechnerisch vollständigen Takten mit musikalisch korrekter Notation.
- Behauptung von Klangtreue allein wegen gleicher Notenzahl und nahezu identischer Einsätze.

## Erlkönig: dokumentierte Fehlversuche (November 2026)
Vier Fassungen wurden vom Anwender in MuseScore als unbrauchbar bewertet: zu viele redundante Stimmen/Pausen, unnatürliche wiederholte Akkordballungen, falsche Handverteilung, viele Hilfslinien, teils klanglich deutlich verschlechtert. Eine nominell 'klangnahe' Fassung mit 1.645 Noten war trotz Notenvollständigkeit nicht musikalisch erfolgreich. Konsequenz: keine weiteren Blind-Konvertierungen; erst 1–4 Takte rekonstruieren und Klang sowie Notenbild kontrollieren.

## Wiederverwendung
Diese Datei zu Beginn jedes konkreten MIDI→MusicXML-Auftrags als Qualitätsstandard heranziehen und nach neuen verifizierten Erkenntnissen fortschreiben. Für langfristige Verbindlichkeit eine Kopie in einem geeigneten Versionsverwaltungs-Repository ablegen; ChatGPT-Erinnerung ist nur eine ergänzende Kurzreferenz.
