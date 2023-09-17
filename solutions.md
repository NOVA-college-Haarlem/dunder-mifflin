markdown

# Queries voor Bestellingen

**1. Toon de 10 vroegste bestellingen in de orders-tabel, inclusief het id, occurred_at en total_amt_usd.**

```sql
SELECT id, occurred_at, total_amt_usd
FROM orders
ORDER BY occurred_at
LIMIT 10;
```

**2. Toon de top 5 bestellingen in termen van het grootste total_amt_usd, inclusief het id, account_id en total_amt_usd.**

```sql

SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd DESC
LIMIT 5;
```

**3. Toon de laagste 20 bestellingen in termen van het kleinste total_amt_usd, inclusief het id, account_id en total_amt_usd.**

```sql

SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd
LIMIT 20;
```







