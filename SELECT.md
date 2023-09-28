# Oplossingen

## SELECT

> 1. Toon de 10 vroegste bestellingen in de orders-tabel, inclusief het id, occurred_at en total_amt_usd.

```sql
SELECT id, occurred_at, total_amt_usd
FROM orders
ORDER BY occurred_at ASC
LIMIT 10;
```

> 2. Toon de top 5 bestellingen in termen van het grootste total_amt_usd, inclusief het id, account_id en total_amt_usd.


```sql
SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd DESC
LIMIT 5;
```

> 3. Toon de laagste 20 bestellingen in termen van het kleinste total_amt_usd, inclusief het id, account_id en total_amt_usd.
```sql
SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd ASC
LIMIT 20;
```

> 4. Schrijf een query die de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor alle bestellingen, eerst gesorteerd op account-ID (in oplopende volgorde) en vervolgens op het totale dollarbedrag (in aflopende volgorde).
```sql
SELECT id AS bestel_ID, account_id AS account_ID, total_amt_usd AS totale_dollarbedrag
FROM orders
ORDER BY account_id ASC, total_amt_usd DESC;
```

> 5. Schrijf nu een query die opnieuw de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor elke bestelling, maar deze keer gesorteerd op het totale dollarbedrag (in aflopende volgorde) en vervolgens op account-ID (in oplopende volgorde).

```sql
SELECT id AS bestel_ID, account_id AS account_ID, total_amt_usd AS totale_dollarbedrag
FROM orders
ORDER BY total_amt_usd DESC, account_id ASC;
```