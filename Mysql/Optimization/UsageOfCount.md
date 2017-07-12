Usage of Count
===

## Using DISTINCT in COUNT Query
### COUNT(DISTINCT col)

That will cost much time for it always sort rather than using hash, so we can using query below instead:
```sql
SELECT COUNT(*) FROM (SELECT DISTINCT column_name FROM table_name) AS temp;
```

*more details can check the quotes[1] in the bottom*






















## Quotes
>[1] https://www.postgresql.org/message-id/CAONnt+72Mtg6kyAFDTHXFWyPPY-QRbAtuREak+64Lm1KN1c-wg@mail.gmail.com
