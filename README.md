# conventions
Coding conventions

## SQL
1. Uppercase Keywords: SQL keywords such as `SELECT`, `FROM`, `LEFT JOIN`, `ON`, `AND`, `WHERE`, `ORDER BY` are written in uppercase. This helps distinguish them from other parts of the query, such as table and column names.
2. Line Breaks: Each part of the query is placed on a new line. This includes the `SELECT` clause, `FROM` clause, `JOIN` clause, `WHERE` clause, and `ORDER BY` clause. This separation makes the query easier to read and understand.
3. Indentation: Clauses that are part of another clause are indented to visually represent the hierarchy. For instance, the column names in the `SELECT` clause, the `ON` and `AND` conditions in the `JOIN` clause, and the conditions in the `WHERE` clause are all indented.
4. Alignment: Operators such as `=` and `AND` in the `ON` and `WHERE` clauses are aligned vertically. This helps in visually relating different parts of the query.
5. Spacing: Adequate spacing between keywords, operators, and identifiers improves the readability of the code.
6. Function names: Use lowercase or camel case, e.g. `max(timestamp)`.

```
import sqlparse

def format_sql(query):
    return sqlparse.format(query, 
                           reindent=True, 
                           keyword_case='upper',
                           identifier_case='lower',
                           comma_first=False)

query = """
    select 
        avg(salary) as average_salary, 
        count(*) as employee_count, 
        max(salary) as max_salary 
    from 
        employees;
"""

print(format_sql(query))

```
