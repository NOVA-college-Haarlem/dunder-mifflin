## WHERE

> 8. Haalt de eerste 5 rijen en alle kolommen uit de bestellingentabel waarbij het dollarbedrag van gloss_amt_usd groter is dan of gelijk aan 1000.

```sql
    SELECT *
    FROM orders
    WHERE gloss_amt_usd >= 1000
    LIMIT 5;
```

> 9. Haalt de eerste 10 rijen en alle kolommen uit de bestellingentabel waarbij het totale dollarbedrag van total_amt_usd kleiner is dan 500.

```sql
    SELECT *
    FROM orders
    WHERE total_amt_usd < 500
    LIMIT 10;
```

> 10. Filter de accounts-tabel om de bedrijfsnaam, website en het primaire contactpunt (primary_poc) te tonen enkel voor het bedrijf Exxon Mobil in de accounts-tabel.

```sql
    SELECT name, website, primary_poc
    FROM accounts
    WHERE name = 'Exxon Mobil';
```
