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

   