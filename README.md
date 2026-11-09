# XAU Safe SMC Signals (TradingView / Pine Script v6)

Indikator für Gold (XAUUSD), der BUY- und SELL-Signale anzeigt. Er setzt auf wenige, dafür gefilterte Setups
(Smart-Money-Konzepte und Price Action).

## Installation
1. TradingView öffnen → unten **Pine Editor**.
2. Inhalt von `XAU_Safe_SMC_Signals.pine` komplett hineinkopieren.
3. **Speichern** → **Zum Chart hinzufügen**.
4. Empfohlen: XAUUSD auf **M5 oder M15** (HTF-Filter steht auf 1H).

## Wann kommt ein BUY? (SELL spiegelbildlich)
| Schritt | Bedingung |
|---|---|
| 1. Liquidity Sweep | Kerze sticht unter ein bestätigtes Swing-Low und schließt wieder darüber (Stop-Hunt) |
| 2. Market Structure Shift | Danach schließt eine Kerze über dem letzten internen Swing-High |
| 3. Fair Value Gap | Nach dem Sweep entsteht ein bullisches FVG (Displacement) |
| 4. Retest | Preis kommt ins FVG zurück und hält dessen Unterkante |
| 5. Price Action | Bullische Bestätigungskerze (Rejection-Wick oder Engulfing) |
| 6. Filter | 1H-EMA-200-Trend, EMA 50/200, London-/NY-Session, News-Spike-Filter, max. SL-Abstand |

- **SL** liegt hinter dem Sweep-Wick plus ATR-Puffer. **TP1** = 1R, **TP2** = 2,5R. Nach TP1 wird der SL auf Break-Even gesetzt.
- Es ist immer nur ein Trade gleichzeitig offen.
- Signale kommen erst **nach Kerzenschluss**, sie repainten also nicht.
- Die Tabelle rechts oben zeigt die Statistik der Signale im sichtbaren Verlauf.

## Alerts
Rechtsklick auf den Chart → **Alarm hinzufügen** → Bedingung „XAU Safe SMC“ → **„Jeder Funktionsaufruf von alert()“**.
Der Alarm enthält dann Entry, SL, TP1 und TP2.

## Wichtig
Kein Indikator ist 100 % sicher. Teste ihn erst auf einem Demokonto und riskiere pro Trade maximal 0,5–1 % deines Kontos.
