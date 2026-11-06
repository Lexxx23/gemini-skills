---
name: lex2
description: Trigger via /lex2 of @lex2 wanneer Lex zegt dat je iets moet leren, opzoeken, tot je nemen of permanent opslaan in de canonieke kennisbank (Infobank) en parate kennis van Lex23.
---

# `/lex2` & `@lex2` — Leren, Opzoeken & Opslaan Protocol (Lex23 + Infobank)

Wanneer Lex `/lex2` of `@lex2` typt (met de bedoeling dat je iets moet leren, opzoeken, tot je nemen of permanent opslaan), voer je direct en zonder tegenvragen dit protocol uit:

## 1. Opzoeken / Tot je nemen (als het nieuwe of externe info is)
- Zoek feiten direct op in de codebase (`grep`/`view_file`), via `tools/infobank.py search "<term>"`, of op het web (`google_search`).

## 2. Deduplicatie-Check (Wet 4: Anti-Duplicatie)
- Draai altijd eerst:
  ```bash
  python3 tools/infobank.py search "<zoekterm>"
  ```
- Staat het er al 100% dekkend in? Meld direct: `STATUS: STAAT ER AL IN` + bestand en regelnummer. Maak nooit dubbele kopieën!

## 3. Permanent Opslaan op de Enige Juiste Plek (Single Source of Truth)
Als het nieuw of gewijzigd is, sla het direct strak en KISS op (of delegeer aan subagent `infobank` / `lex2`):
- **Systeem, host, poort, domein, DNS, CLI, MCP of login-locatie** → [`docs/projectkennis/ai-en-systeem-onboarding.md`](../../../docs/projectkennis/ai-en-systeem-onboarding.md)
- **Harde werkafspraak, grens of gedrag** → [`AGENTS.md`](../../../AGENTS.md)
- **Architectuur- of technisch besluit** → [`DECISIONS.md`](../../../DECISIONS.md)
- **Handelsstrategie, SMC/FJ-inzicht of chart-regel** → [`docs/projectkennis/strategie-en-chart.md`](../../../docs/projectkennis/strategie-en-chart.md)
- **Parate Kern van Lex23** → Update ook `lex-2/agent.md` en `~/.gemini/agents/lex-2.md` als Lex23 het altijd direct paraat moet hebben.

## 4. Terugkoppeling aan Lex (Max 4 regels, geen keuzestress)
- `STATUS: GELEERD & OPGESLAGEN (of STAAT ER AL IN)`
- `WAAR: <bestand + regel>`
- `KERN: <1 zin wat er nu vastligt>`
