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

5. SQL Query | Calculate number of weekdays between two dates | Exclude Weekends | DateDiff | DateName

#### DATENAME
```select datename(dw, "2017/08/25") as dateNameOfTheWeek```

output: Friday

#### DATEDIFF (interval, date1, date2)
```select datediff(year, "2017/08/25", "2019/08/25") as diffInYear```

6. SQL Tutorial | Date Functions | Find Age from Birth Date \
(we are using a case when here because to get the exact age)

#### GETDATE ()

getdate() -> 2022-05-25 18:53:53.683

#### DATEADD(inerval, number, date) 
``` select DATEADD(YEAR, 1, GETDATE()) AS TodayAdd1Year```

<img width="421" alt="image" src="https://user-images.githubusercontent.com/36904516/170336430-e1c5b782-6448-4e25-a1bd-ca9cc5f861b6.png">

7. SQL Query | How to check for Alphanumeric values | Like | Wildcards

#### wildcard

% 0 or more char \
_ 1 char \
[] single char in the brackets -> h[oa]t \
^ char not in the brackets h[^oa]t \
'-' range \

8. SQL Query | Remove leading and trailing zeroes from a decimal

<img width="386" alt="image" src="https://user-images.githubusercontent.com/36904516/170345121-ff6b4570-f67e-4d73-8b28-3e3fb2bebde8.png">

9. SQL Query | How to Extract Numbers and Alphabets from an alphanumeric string | Translate function

#### TRANSLATE(STRING, CHAR, TRANSLATIONS)

** TRANSLATE() function will return an error if chars and translations have different lengths.**

```select translate('I am Ling', 'Ling', 'LingLing')``` \
Output -> 'I am LingLing'

<img width="338" alt="image" src="https://user-images.githubusercontent.com/36904516/170346555-0dac1931-cbf1-47a6-9ed5-aaf9f5d5cbb4.png">

<img width="742" alt="image" src="https://user-images.githubusercontent.com/36904516/170347625-fee539a2-a4ad-453e-8573-e9dcd98ed558.png">

10. SQL Query | How to calculate Running Totals and Cumulative Sum ?

sum(salary) over( order by firstname, lastname) -> ** whatever we order by need to be unique to make the cummulative sum count for it, if we only order by firstname, when we have duplicate firstnames, the salary will be ignored. **

11. SQL Query | How to calculate YTD and MTD totals | Window Functions

Adding a ```rows between unbonded proceding and current row``` fixed the issie that highted in yellow below.
<img width="419" alt="image" src="https://user-images.githubusercontent.com/36904516/170352156-f585703f-ee1a-4719-9b01-a1bb83bb3c5e.png">


