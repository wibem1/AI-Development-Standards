# Bewertung spezialisierter KI-Entwicklungsagenten
Stand: 24. Oktober 2026 · vorläufige Empfehlung, **kein erfolgreicher Praxistest**

## Anlass
Zwei neue ChatGPT-Chats leiteten trotz GitHub-Projektgedächtnis unterschiedliche VectorCraft-Arbeitsschritte ab. GitHub-Speicherung allein garantiert weder gleichen Aufgabenfokus noch technisch begrenzte Ausführung.

## Ergebnis
- Das bisherige System eignet sich zur dauerhaften Information, **nicht allein** zur verbindlichen Auftragssteuerung.
- Bei Spezialagenten wie **Codex CLI** und **Claude Code** stehen direkter Repository-Kontext, planbare Berechtigungen sowie echte Arbeitsverzeichnisse/Tests zur Verfügung. Auch dort ist die semantische Befolgung einer Anweisung nicht garantiert.
- **Vorläufig Codex zuerst prüfen:** in Plus nutzbar, teilt jedoch ChatGPT-Work-Kontingent; keine zusätzlichen Credits freigeben. Claude Code als Vergleich offenhalten, derzeit kein zwingender Zusatzkauf.
- Es fehlt ein verbindlicher *aktueller Auftrag* mit eindeutigen Grenzen und überprüfbaren Freigaben. Eine Datei allein ist noch keine technisch erzwungene Sperre.
- Zwischen Entwicklungsagent und produktivem Repository sind zweckmäßige Berechtigungen, isolierter Branch/Arbeitsbereich und getrennte Übernahme des getesteten Ergebnisses erforderlich.

## Minimaler Praxisvergleich (noch NICHT durchgeführt)
1. **Nur lesend starten:** Agent öffnet das Projekt, benennt aktuellen freigegebenen Auftrag, vorhandene Belege und ausdrücklich verbotene Arbeiten.
2. **Keine Programmierung in Phase 1**; keine GitHub Actions, Provider-Abfragen, Releases, API-Kosten oder Commits.
3. Prüfen, ob AGENTS.md/PROJECT_STATE.md und eine zukünftig festzulegende CURRENT_TASK.md tatsächlich gelesen wurden, statt nur allgemeine Vorgehensweisen wiederzugeben.
4. In Phase 2 **ein einziges isoliertes, reversibles Testziel** in einem getrennten Arbeitsbereich; vorab Akzeptanzkriterium und technische Werkzeug-/Schreibgrenzen prüfen.
5. Misslungener oder ungeklärter Versuch: alte geprüfte Referenz unverändert lassen. Nicht in wiederholte Builds ausweichen.
6. Erst nach Vergleich entscheiden, ob Codex oder Claude Code die reguläre Entwicklungsumgebung wird.

## Quellen
- https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex
- https://developers.openai.com/cookbook/examples/gpt-5/codex_prompting_guide
- https://developers.openai.com/blog/codex-as-a-platform
- https://developers.openai.com/de-DE/docs/pricing
- https://code.claude.com/docs/de/communications-kit

Diese Datei beschreibt eine Empfehlung, **keine Änderung der bisher dokumentierten VectorCraft-Neustart-Strategie** und keine technische Umsetzung von Berechtigungssperren.
