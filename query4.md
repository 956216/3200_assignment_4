### AI Disclaimer
- I asked Gemini 3 Thinking (Web):
    - explain in SQL the difference between HAVING and WHERE
    - I asked because I had heard of both before, and wasn't sure which to use in this instance
    - It said that WHERE is before grouping, and HAVING is after grouping

### QUERY 4
```SQL
SELECT
  customers.State,
  COUNT(*) AS UniqueCustomers
FROM customers
GROUP BY customers.State
HAVING COUNT(*) > 10
ORDER BY customers.State;
```
As per what Gemini said, I used HAVING, because we're checking the count *after* we group the customers by state. ORDER BY comes last because we only order once we have all of our data ready to display.

### RESULTS
```
|29
```

It appears that non-null states have more than 10 customers
