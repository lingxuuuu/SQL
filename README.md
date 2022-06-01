# SQL

#### sql is not case sensitive (sql = SQL)

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

<img width="467" alt="image" src="https://user-images.githubusercontent.com/36904516/170353064-3428103a-d760-4da0-a802-89bd757fe282.png">

12. SQL- Find employees with salary less than Dept average but more than average of any other Dept | ANY

<img width="712" alt="image" src="https://user-images.githubusercontent.com/36904516/170354746-cbfa839e-1a32-4690-816c-d1207e949272.png">

13. SQL Query | How to generate a two digit alphabetic sequence | Cycle through alphabets

<img width="465" alt="image" src="https://user-images.githubusercontent.com/36904516/170384449-495f46d6-546a-4791-a000-7e1bdabb43b2.png">

14. SQL Query | Convert data from columns into Rows | Unpivot

<img width="507" alt="image" src="https://user-images.githubusercontent.com/36904516/170385063-a65644df-3c41-456f-8b96-80976a547688.png">

15. SQL Query | How to convert data from rows into comma separated single column | FOR XML PATH | STUFF

<img width="467" alt="image" src="https://user-images.githubusercontent.com/36904516/170403733-602f913e-64cf-4f64-93e1-583df99c8798.png">

<img width="637" alt="image" src="https://user-images.githubusercontent.com/36904516/170403969-7c76ab39-039c-421d-9758-46b060480f40.png">

<img width="569" alt="image" src="https://user-images.githubusercontent.com/36904516/170404122-cedb2f63-dbaa-433f-89ee-5e80207142a8.png">

#### stuff(string, start, length, new_string)

```select stuff('SQL Tutorial', 1, 3, 'HTML') -> 'HTML tutorial'```

<img width="698" alt="image" src="https://user-images.githubusercontent.com/36904516/170404860-4b473025-1185-40bd-b648-8d45082a21cd.png">

16. SQL Query Interview Questions | How to capitalize first letter of a string

<img width="670" alt="image" src="https://user-images.githubusercontent.com/36904516/170406216-bc1d59cd-e41b-4b87-a31c-1466d7b28683.png">

17. SQL Query | Count the occurrence of a character in a string

<img width="741" alt="image" src="https://user-images.githubusercontent.com/36904516/170622311-c18ffdb1-800e-4f92-b16a-87a0e1482702.png">

18. SQL Interview Query | Find names that start/end with 'a' | More examples | Like | Pattern Matching

<img width="413" alt="image" src="https://user-images.githubusercontent.com/36904516/170623810-cb6ab2aa-5f7c-4436-8073-1e961efffab1.png">

<img width="433" alt="image" src="https://user-images.githubusercontent.com/36904516/170623965-f7bd8dbe-7455-4cf6-8969-16c74d155d56.png">

19. SQL Interview Question | How to find departments having only male / female employees?

<img width="342" alt="image" src="https://user-images.githubusercontent.com/36904516/170624570-414b8846-95c8-485c-bae9-ad714f7e9d25.png">

Solution 2: \
<img width="578" alt="image" src="https://user-images.githubusercontent.com/36904516/170625337-785965f8-e839-4011-829b-051cd467893d.png">

20. SQL Interview Question | How to find strings with lower case characters | Case Insensitive | Collate \
SQL is not case sensitive, ```COLLATE Latin1_General_CS_AS``` will make SQL case sensitive

<img width="638" alt="image" src="https://user-images.githubusercontent.com/36904516/170626123-2871c61d-67c9-4e16-a0bb-f481fd19dccb.png">

21. SQL Query | How to find Maximum of multiple columns | Values

<img width="395" alt="image" src="https://user-images.githubusercontent.com/36904516/170792478-915dab67-fa3c-44ca-adf0-c8d38991e385.png">

<img width="440" alt="image" src="https://user-images.githubusercontent.com/36904516/170792576-faf6b44e-ca09-43ff-95b8-d3cefe3996cc.png">

<img width="761" alt="image" src="https://user-images.githubusercontent.com/36904516/170792655-ade04410-afe9-47d2-b1d3-3de3b6079e0f.png">

22. SQL tutorial | How to find n consecutive date records | Sales for at least n consecutive days.

<img width="726" alt="image" src="https://user-images.githubusercontent.com/36904516/170794223-9652419d-1fbe-4290-9ece-9d3b3024cdd4.png">

23. SQL Query Interview Question - Scenario - No sales for n consecutive days | Identify date gaps

<img width="733" alt="image" src="https://user-images.githubusercontent.com/36904516/170798939-0fa87c05-b15c-4819-9450-0ef89918e057.png">

24. SQL Query | Compare monthly sales with previous month, same month previous year, first month of year

```SELECT YEAR('2017/08/25') AS Year;```

```year(); month(); day()```

<img width="635" alt="image" src="https://user-images.githubusercontent.com/36904516/170839640-4b0760d6-c065-4d23-ac6e-b224980e5ac2.png">

<img width="723" alt="image" src="https://user-images.githubusercontent.com/36904516/170839718-c8acb230-3365-450b-b6c3-9e8e3d01ad04.png">

25. SQL Interview Questions | How to find number of emails from the same domain | CharIndex

#### CharIndex() CHARINDEX(substring, string, start)

<img width="467" alt="image" src="https://user-images.githubusercontent.com/36904516/170839830-2e76e49d-2985-4b6b-856e-220e96f02c28.png">

<img width="706" alt="image" src="https://user-images.githubusercontent.com/36904516/170840932-5b4eb2ea-0dde-4f28-bc74-e53a598a7421.png">

26. SQL Query to find a leap year | 2 methods | SQL Interview Questions

#### isdate() checks an expression and return 1 if it is a valid date, otherwise 0

<img width="436" alt="image" src="https://user-images.githubusercontent.com/36904516/171298295-d074162b-c9f6-4d7e-99af-db7e36c92e86.png">

<img width="536" alt="image" src="https://user-images.githubusercontent.com/36904516/171298481-50862021-1bd4-489b-a32c-ec3fe5d6e156.png">

27. What is the difference between Translate and Replace

<img width="505" alt="image" src="https://user-images.githubusercontent.com/36904516/171303375-f8014a10-c149-4439-b379-805546b59a10.png">

<img width="488" alt="image" src="https://user-images.githubusercontent.com/36904516/171303693-8603399b-02a8-4fac-8d78-7ce7f2919a8b.png">

<img width="413" alt="image" src="https://user-images.githubusercontent.com/36904516/171303784-5a5c3625-46b8-41f6-a1b8-977c356bed08.png">

<img width="713" alt="image" src="https://user-images.githubusercontent.com/36904516/171303911-5803a14c-74d9-4cf7-bf93-891aa247a43e.png">
