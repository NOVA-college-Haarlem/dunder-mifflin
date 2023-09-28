> 11. Maak een kolom die de standard_amt_usd deelt door de standard_qty om de eenheidsprijs voor standaard papier voor elke bestelling te vinden. Beperk de resultaten tot de eerste 10 bestellingen en neem de id en account_id velden op.

```sql
   SELECT id, account_id, standard_amt_usd/standard_qty AS unit_price
    FROM orders
    LIMIT 10;
```

> 12. Schrijf een query die het percentage van de omzet vindt dat afkomstig is van posterpapier voor elke bestelling. Je zult alleen de kolommen moeten gebruiken die eindigen op \_usd. (Probeer dit te doen zonder de totale kolom te gebruiken.) Toon ook de id en account_id velden. OPMERKING - je zult een foutmelding ontvangen met de juiste oplossing voor deze vraag. Dit komt omdat ten minste een van de waarden in de gegevens een deling door nul veroorzaakt in je formule. Je zult later in de cursus leren hoe je dit probleem volledig kunt aanpakken. Voor nu kun je je berekeningen gewoon beperken tot de eerste 10 bestellingen, zoals we deden in vraag #1, en je zult die set gegevens vermijden die het probleem veroorzaakt.

```sql
   SELECT id, account_id,
           poster_amt_usd/(standard_amt_usd + gloss_amt_usd + poster_amt_usd) AS post_per
    FROM orders
    LIMIT 10;
```

Merk op, de bovenstaande operatoren combineren informatie over kolommen voor dezelfde rij. Als je waarden van een bepaalde kolom wilt combineren, over meerdere rijen, dan doen we dit met aggregaties. We komen hierop terug voor het einde van de cursus!
