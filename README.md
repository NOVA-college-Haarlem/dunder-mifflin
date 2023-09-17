# OEFENEN


## SELECT

**1. Toon de 10 vroegste bestellingen in de orders-tabel, inclusief het id, occurred_at en total_amt_usd.**
**2. Toon de top 5 bestellingen in termen van het grootste total_amt_usd, inclusief het id, account_id en total_amt_usd.**
**3. Toon de laagste 20 bestellingen in termen van het kleinste total_amt_usd, inclusief het id, account_id en total_amt_usd.**



Write a query that displays the order ID, account ID, and total dollar amount for all the orders, sorted first by the account ID (in ascending order), and then by the total dollar amount (in descending order).

Now write a query that again displays order ID, account ID, and total dollar amount for each order, but this time sorted first by total dollar amount (in descending order), and then by account ID (in ascending order).

Compare the results of these two queries above. How are the results different when you switch the column you sort on first?

Solutions to previous ORDER BY Questions

    Write a query that displays the order ID, account ID, and total dollar amount for all the orders, sorted first by the account ID (in ascending order), and then by the total dollar amount (in descending order).

SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY account_id, total_amt_usd DESC;

    Now write a query that again displays order ID, account ID, and total dollar amount for each order, but this time sorted first by total dollar amount (in descending order), and then by account ID (in ascending order).

SELECT id, account_id, total_amt_usd
FROM orders
ORDER BY total_amt_usd DESC, account_id;

    Compare the results of these two queries above. How are the results different when you switch the column you sort on first?
    In query #1, all of the orders for each account ID are grouped together, and then within each of those groupings, the orders appear from the greatest order amount to the least. In query #2, since you sorted by the total dollar amount first, the orders appear from greatest to least regardless of which account ID they were from. Then they are sorted by account ID next. (The secondary sorting by account ID is difficult to see here, since only if there were two orders with equal total dollar amounts would there need to be any sorting by account ID.)



Questions

Write a query that:

    Pulls the first 5 rows and all columns from the orders table that have a dollar amount of gloss_amt_usd greater than or equal to 1000.

    Pulls the first 10 rows and all columns from the orders table that have a total_amt_usd less than 500.

    Solution from previous WHERE Questions

    SELECT *
    FROM orders
    WHERE gloss_amt_usd >= 1000
    LIMIT 5;

    SELECT *
    FROM orders
    WHERE total_amt_usd < 500
    LIMIT 10;

    Practice Question Using WHERE with Non-Numeric Data

    Filter the accounts table to include the company name, website, and the primary point of contact (primary_poc) just for the Exxon Mobil company in the accounts table.

    Solution from WHERE with Non-Numeric Data

    SELECT name, website, primary_poc
    FROM accounts
    WHERE name = 'Exxon Mobil';

Note: If you received an error message when executing your query, remember that SQL requires single-quotes, not double-quotes, around text values like 'Exxon Mobil.'

Questions using Arithmetic Operations

Using the orders table:

    Create a column that divides the standard_amt_usd by the standard_qty to find the unit price for standard paper for each order. Limit the results to the first 10 orders, and include the id and account_id fields.

    Write a query that finds the percentage of revenue that comes from poster paper for each order. You will need to use only the columns that end with _usd. (Try to do this without using the total column.) Display the id and account_id fields also. NOTE - you will receive an error with the correct solution to this question. This occurs because at least one of the values in the data creates a division by zero in your formula. You will learn later in the course how to fully handle this issue. For now, you can just limit your calculations to the first 10 orders, as we did in question #1, and you'll avoid that set of data that causes the problem.

Notice, the above operators combine information across columns for the same row. If you want to combine values of a particular column, across multiple rows, we will do this with aggregations. We will get to that before the end of the course!

Solutions to Arithmetic Operator Questions

    SELECT id, account_id, standard_amt_usd/standard_qty AS unit_price
    FROM orders
    LIMIT 10;

    SELECT id, account_id,
           poster_amt_usd/(standard_amt_usd + gloss_amt_usd + poster_amt_usd) AS post_per
    FROM orders
    LIMIT 10;


Questions using the LIKE operator

Use the accounts table to find

    All the companies whose names start with 'C'.

    All companies whose names contain the string 'one' somewhere in the name.

    All companies whose names end with 's'.

    Solutions for LIKE operator

    SELECT name
    FROM accounts
    WHERE name LIKE 'C%';

    SELECT name
    FROM accounts
    WHERE name LIKE '%one%';

    SELECT name
    FROM accounts
    WHERE name LIKE '%s';

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

SELECT *
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


