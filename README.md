# OEFENEN

## SELECT

> 1. Toon de 10 vroegste bestellingen in de orders-tabel, inclusief het id, occurred_at en total_amt_usd.

> 2. Toon de top 5 bestellingen in termen van het grootste total_amt_usd, inclusief het id, account_id en total_amt_usd.

> 3. Toon de laagste 20 bestellingen in termen van het kleinste total_amt_usd, inclusief het id, account_id en total_amt_usd.

> 4. Schrijf een query die de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor alle bestellingen, eerst gesorteerd op account-ID (in oplopende volgorde) en vervolgens op het totale dollarbedrag (in aflopende volgorde).

> 5. Schrijf nu een query die opnieuw de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor elke bestelling, maar deze keer gesorteerd op het totale dollarbedrag (in aflopende volgorde) en vervolgens op account-ID (in oplopende volgorde).

Vergelijk de resultaten van deze twee bovenstaande queries. Hoe verschillen de resultaten wanneer u de kolom waarop u eerst sorteert, wijzigt?

## ORDER BY

> 6. Schrijf een query die de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor alle bestellingen, eerst gesorteerd op account-ID (in oplopende volgorde) en vervolgens op het totale dollarbedrag (in aflopende volgorde).

> 7. Schrijf nu een query die opnieuw de bestel-ID, het account-ID en het totale dollarbedrag weergeeft voor elke bestelling, maar deze keer gesorteerd op het totale dollarbedrag (in aflopende volgorde) en vervolgens op account-ID (in oplopende volgorde).

Vergelijk de resultaten van deze twee queries hierboven. Hoe verschillen de resultaten wanneer je de kolom waarop je eerst sorteert, wisselt?

## WHERE

> 8. Haalt de eerste 5 rijen en alle kolommen uit de bestellingentabel waarbij het dollarbedrag van gloss_amt_usd groter is dan of gelijk aan 1000.

> 9. Haalt de eerste 10 rijen en alle kolommen uit de bestellingentabel waarbij het totale dollarbedrag van total_amt_usd kleiner is dan 500.

> 10. Filter de accounts-tabel om de bedrijfsnaam, website en het primaire contactpunt (primary_poc) te tonen enkel voor het bedrijf Exxon Mobil in de accounts-tabel.

## Wiskundige operatoren

Gebruik de orders table:

> 11. Maak een kolom die de standard_amt_usd deelt door de standard_qty om de eenheidsprijs voor standaard papier voor elke bestelling te vinden. Beperk de resultaten tot de eerste 10 bestellingen en neem de id en account_id velden op.

> 12. Schrijf een query die het percentage van de omzet vindt dat afkomstig is van posterpapier voor elke bestelling. Je zult alleen de kolommen moeten gebruiken die eindigen op \_usd. (Probeer dit te doen zonder de totale kolom te gebruiken.) Toon ook de id en account_id velden. OPMERKING - je zult een foutmelding ontvangen met de juiste oplossing voor deze vraag. Dit komt omdat ten minste een van de waarden in de gegevens een deling door nul veroorzaakt in je formule. Je zult later in de cursus leren hoe je dit probleem volledig kunt aanpakken. Voor nu kun je je berekeningen gewoon beperken tot de eerste 10 bestellingen, zoals we deden in vraag #1, en je zult die set gegevens vermijden die het probleem veroorzaakt.

## Like

Gebruik de _accounts_ tabel

> 13. Alle bedrijven waarvan de namen beginnen met 'C'.

> 14. Alle bedrijven waarvan de namen ergens in de naam de tekenreeks 'one' bevatten.

> 15. Alle bedrijven waarvan de namen eindigen op 's'.

## IN

Questions using IN operator

    Use the accounts table to find the account name, primary_poc, and sales_rep_id for Walmart, Target, and Nordstrom.

    Use the web_events table to find all information regarding individuals who were contacted via the channel of organic or adwords.

    Solutions to IN Questions

    SELECT name, primary_poc, sales_rep_id
    FROM accounts
    WHERE name IN ('Walmart', 'Target', 'Nordstrom');

    SELECT *
    FROM web_events
    WHERE channel IN ('organic', 'adwords');

Questions using the NOT operator

We can pull all of the rows that were excluded from the queries in the previous two concepts with our new operator.

    Use the accounts table to find the account name, primary poc, and sales rep id for all stores except Walmart, Target, and Nordstrom.

    Use the web_events table to find all information regarding individuals who were contacted via any method except using organic or adwords methods.

Use the accounts table to find:

    All the companies whose names do not start with 'C'.

    All companies whose names do not contain the string 'one' somewhere in the name.

    All companies whose names do not end with 's'.

Solutions to NOT IN Questions

    SELECT name, primary_poc, sales_rep_id
    FROM accounts
    WHERE name NOT IN ('Walmart', 'Target', 'Nordstrom');

    SELECT *
    FROM web_events
    WHERE channel NOT IN ('organic', 'adwords');

Solutions to NOT LIKE Questions

    SELECT name
    FROM accounts
    WHERE name NOT LIKE 'C%';

    SELECT name
    FROM accounts
    WHERE name NOT LIKE '%one%';

    SELECT name
    FROM accounts
    WHERE name NOT LIKE '%s';

Questions using AND and BETWEEN operators

    Write a query that returns all the orders where the standard_qty is over 1000, the poster_qty is 0, and the gloss_qty is 0.

    Using the accounts table, find all the companies whose names do not start with 'C' and end with 's'.

    When you use the BETWEEN operator in SQL, do the results include the values of your endpoints, or not? Figure out the answer to this important question by writing a query that displays the order date and gloss_qty data for all orders where gloss_qty is between 24 and 29. Then look at your output to see if the BETWEEN operator included the begin and end values or not.

    Use the web_events table to find all information regarding individuals who were contacted via the organic or adwords channels, and started their account at any point in 2016, sorted from newest to oldest.

    Solutions to AND and BETWEEN Questions

    Write a query that returns all the orders where the standard_qty is over 1000, the poster_qty is 0, and the gloss_qty is 0.

    SELECT *
    FROM orders
    WHERE standard_qty > 1000 AND poster_qty = 0 AND gloss_qty = 0;

    Using the accounts table, find all the companies whose names do not start with 'C' and end with 's'.

SELECT name
FROM accounts
WHERE name NOT LIKE 'C%' AND name LIKE '%s';

    When you use the BETWEEN operator in SQL, do the results include the values of your endpoints, or not? Figure out the answer to this important question by writing a query that displays the order date and gloss_qty data for all orders where gloss_qty is between 24 and 29. Then look at your output to see if the BETWEEN operator included the begin and end values or not.

SELECT occurred_at, gloss_qty
FROM orders
WHERE gloss_qty BETWEEN 24 AND 29;

You should notice that there are a number of rows in the output of this query where the gloss_qty values are 24 or 29. So the answer to the question is that yes, the BETWEEN operator in SQL is inclusive; that is, the endpoint values are included. So the BETWEEN statement in this query is equivalent to having written "WHERE gloss_qty >= 24 AND gloss_qty <= 29."

4. You will notice that using BETWEEN is tricky for dates! While BETWEEN is generally inclusive of endpoints, it assumes the time is at 00:00:00 (i.e. midnight) for dates. This is the reason why we set the right-side endpoint of the period at '2017-01-01'.

SELECT \*
FROM web_events
WHERE channel IN ('organic', 'adwords') AND occurred_at BETWEEN '2016-01-01' AND '2017-01-01'
ORDER BY occurred_at DESC;

Questions using the OR operator

    Find list of orders ids where either gloss_qty or poster_qty is greater than 4000. Only include the id field in the resulting table.

    Write a query that returns a list of orders where the standard_qty is zero and either the gloss_qty or poster_qty is over 1000.

    Find all the company names that start with a 'C' or 'W', and the primary contact contains 'ana' or 'Ana', but it doesn't contain 'eana'.

    Solutions to OR Questions

    SELECT id
    FROM orders
    WHERE gloss_qty > 4000 OR poster_qty > 4000;

    SELECT *
    FROM orders
    WHERE standard_qty = 0 AND (gloss_qty > 1000 OR poster_qty > 1000);

    SELECT *
    FROM accounts
    WHERE (name LIKE 'C%' OR name LIKE 'W%')
                  AND ((primary_poc LIKE '%ana%' OR primary_poc LIKE '%Ana%')
                  AND primary_poc NOT LIKE '%eana%');
