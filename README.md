# SQL

#### SQL Query Interview Questions

1. SQL Query | Custom Sorting | Order by Month in an Year

<img width="370" alt="image" src="https://user-images.githubusercontent.com/36904516/170147575-5f749ede-dd68-4111-ab50-4fc0c30f2959.png">

```DATENAME(interval,date)```
```month(date)```

<img width="499" alt="image" src="https://user-images.githubusercontent.com/36904516/170148353-7cab24ef-d724-4eb6-a121-f3139415c483.png">

2. SQL Query | Compare with Previous Quarter's sales | Analytical Functions | Lead | Lag

<img width="443" alt="image" src="https://user-images.githubusercontent.com/36904516/170149098-3e1032c5-bf9f-4a91-9402-c3c0a266bdca.png">

<img width="434" alt="image" src="https://user-images.githubusercontent.com/36904516/170149320-6095d225-4c2b-487e-9acf-79eeda4f8367.png">

<img width="463" alt="image" src="https://user-images.githubusercontent.com/36904516/170149601-31a8a556-7d57-4fe1-b5b3-7acd8dd9e2c7.png">

3. SQL Query | Split Concatenated String into Columns | CharIndex

```charIndex(substring, string, start)```

<img width="347" alt="image" src="https://user-images.githubusercontent.com/36904516/170150130-ba9b39ac-815c-4b55-9539-2c638462d10e.png">

```string_split()```
string_split is always used with cross apply, example:

```
select first_name, last_name, VALUE phone
from sales.contacts
CROSS APPLY STRING_SPLIT(phones, ',')
```

<img width="407" alt="image" src="https://user-images.githubusercontent.com/36904516/170156158-8ea2b4ca-9d72-4735-9e13-4402e6988c2e.png">

4. SQL Query | Replace special characters | Control Characters | REPLACE function

<img width="558" alt="image" src="https://user-images.githubusercontent.com/36904516/170165562-6d652c91-9bf5-4fea-9dfe-a7dc5e994949.png">

