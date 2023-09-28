> 6. Schrijf een query die de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor alle bestellingen, eerst gesorteerd op account-ID (in oplopende volgorde) en vervolgens op het totale dollarbedrag (in aflopende volgorde).

```sql
SELECT id AS order_ID, account_id AS account_ID, total_amt_usd AS total_dollar_amount
FROM orders
ORDER BY account_id ASC, total_amt_usd DESC;
```

> 7. Schrijf nu een query die opnieuw de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor elke bestelling, maar deze keer gesorteerd op het totale dollarbedrag (in aflopende volgorde) en vervolgens op account-ID (in oplopende volgorde).

```sql
SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd DESC, account_id;
```

Vergelijk de resultaten van deze twee queries hierboven. Hoe verschillen de resultaten wanneer je de kolom waarop je eerst sorteert, wisselt?

The translation of your request into Dutch is:

In query #1 zijn alle bestellingen voor elk account-ID gegroepeerd, en binnen elk van die groeperingen verschijnen de bestellingen van het grootste bestelbedrag naar het kleinste. In query #2, omdat je eerst gesorteerd hebt op het totale dollarbedrag, verschijnen de bestellingen van groot naar klein, ongeacht van welk account-ID ze afkomstig waren. Vervolgens worden ze gesorteerd op account-ID. (Het secundair sorteren op account-ID is hier moeilijk te zien, aangezien er alleen gesorteerd zou moeten worden op account-ID als er twee bestellingen waren met gelijke totale dollarbedragen.)

