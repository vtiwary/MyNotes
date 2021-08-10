![image](https://user-images.githubusercontent.com/24499265/128815003-f831333b-3362-4799-9406-98a7ffeadee2.png)
Here the statement if inside bracket this a list of statements.. Effect in each to tell wheather it allows or denies anything..AWS starts with implicit deny
i.e. starts with zero permission.
in picture above holiady/* signifies that it's applicable to the objects inside the bucket

Condition : This is an AND condition "Condition": {
            "DateGreaterThan": {"aws:CurrentTime": "2020-12-01T00:00:00Z"},
            "DateLessThan": {"aws:CurrentTime": "2020-12-25T06:00:00Z"}
so, if above condition is match, whole deny will become true and effective

