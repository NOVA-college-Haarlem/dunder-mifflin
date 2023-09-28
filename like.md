## Like

Gebruik de _accounts_ tabel

> 13. Alle bedrijven waarvan de namen beginnen met 'C'.

```sql
    SELECT name
    FROM accounts
    WHERE name LIKE 'C%';
```

> 14. Alle bedrijven waarvan de namen ergens in de naam de tekenreeks 'one' bevatten.

```sql

    SELECT name
    FROM accounts
    WHERE name LIKE '%one%';
```

> 15. Alle bedrijven waarvan de namen eindigen op 's'.

```sql
    SELECT name
    FROM accounts
    WHERE name LIKE '%s';
```
