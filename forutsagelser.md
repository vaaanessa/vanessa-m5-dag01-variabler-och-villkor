# Förutsägelser (steg 8)

Skriv din gissning FÖRST. Skriv sedan raden i STEG 7 i `src/main.ts`, kör den och fyll i vad som hände. Skriv också vad TypeScript sa (ofta understryker den raden).

| Uttryck             | Min gissning | Det som hände       | Vad sa TypeScript? | Hade jag rätt? |
| ------------------- | ------------ | ------------------- | ------------------ | -------------- |
| `"5" + 3`           | 53           | 53                  | Inget typfel       | Ja             |
| `"5" - 3`           | 2            | 2                   | Typfel             | Ja             |
| `true + 1`          | true         | 2                   | Typfel             | Nej            |
| `0.1 + 0.2`         | 0.3          | 0.30000000000000004 | Inget typfel       | Nej            |
| `"" === 0`          | false        | false               | Typfel             | Ja             |
| `null == undefined` | object       | true                | Inget typfel       | Nej            |

## Min regel för det jag missade

1. (true + 1) När JavaScript räknar med true (sant) i det här uttrycket blir det 1 + 1, alltså 2.
2. (0.1 + 0.2) JavaScript lagrar vissa decimaltal ungefärligt. Därför visade 0.1 + 0.2 en pytteliten skillnad från 0.3.
3. (null == undefined) Med == räknas null och undefined som lika, så jämförelsen ger true (sant).

## Tänk efter

1. ("5" - 3) Typfel. TypeScript markerade "5" eftersom det är text.
2. (true + 1) Typfel. + kan inte användas mellan boolean och number.
3. ("" ===0) Typfel. TypeScript visar ett fel eftersom jag jämför tom text med talet noll.

TypeScript kan upptäcka typfel innan koden körs. Om koden ändå körs i webbläsaren är det JavaScripts regler som avgör resultatet. Till exempel markerar TypeScript "5" - 3 som ett typfel, men JavaScript gör om texten "5" till talet 5 och får svaret 2.
