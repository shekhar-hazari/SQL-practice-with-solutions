# SQL-practice-with-solutions
This repository will help you go through basic sql required to extract data from an Oracle Database. This is closely related to day-to-day queries you will see in life unless you are not a Data Engineer or in a job which requires very complex SQL queries. It is a fun practice to go through if you'd like brush up on your concepts. Pay attention to small details while solving the problems, as the question may ask something very specific for which you might have to write nested queries.

The relational schema for the Academics database is as follows:
DEPARTMENT(deptnum, descrip, instname, deptname, state, postcode)
ACADEMIC(acnum, deptnum*, famname, givename, initials, title)
PAPER(panum, title)
AUTHOR(panum*, acnum*)
FIELD(fieldnum, id, title)
INTEREST(fieldnum*, acnum*, descrip)
Some notes on the Academics database:
• An academic department belongs to one institution (instname) and often has many academics. An academic only works for one department.
• Research papers (PAPER) are often authored by several academics, and of course an academic often writes several papers (AUTHOR).
• A research field (FIELD) often attracts many academics and an academic can have interest in several research fields (INTEREST).

Note: This assignment is done on Oracle DB, please make changes to queries according to the database you are using.
Run the academics.sql file before you begin to solve the questions, this will load the database required for solving the questions.

1. Find departments that have a description (descrip) available in the database. Return all details of these departments.
2. List the paper number and title of papers by the academic whose acnum is 100.
3. For each academic, give the acnum, givename, famname and the total number of papers s/he has written. Note that if an academic has not written any paper, his/her total should be zero. You can use JOIN operators such as NATURAL, JOIN ...ON.
4. The research field ID is a research field classification code representing classes for three “Levels”. These three Levels are separated by a “full stop” in a single string. For example the research field ID “B.1.6” represents that the research field belongs to Class “B” for Level one, Class “1” for Level two and Class “6” for Level three. For research fields in Class “1” for Level two, list the field IDs and the number of academics for each field ID.
5. Find departments where at least one academic does not have research interest, and list the deptnum, depntname, instname of these departments. Must use a subquery.
6. Output in alphabetical order the acnum, famname, givename, and department number (deptnum), and description (descrip) of authors whose family name starts with “C”.
7. List the fieldnum, title, and total number of interested academics (under the heading "NO. ACADEMICS INTERESTED") in each research field, in increasing order (i.e. ascending order) of fieldnum.
8. List in alphabetical order the institution and name of departments where at least 10 academics have written papers.
9. List the deptnum of departments whose postcodes are in the range 3000..3999 and that do not have any academics with the title of Professor (stored as “Prof” or “Prof.” in the database) , including departments that do not have any academics.
10. Find the departments that have produced at least ten papers (that is, those departments where the sum of papers written by their academics is at least ten). Output their deptnum and deptname in ascending order.
11. List the deptnum and deptname of departments whose academics have never written any papers.
12. List papers (panum) by academics with research interests in fields related to "data". You must use EXISTS. Note that “fields related to data” includes any occurrence of the four letters “data” within a field name, in any case.
13. The popularity of a field is measured by the number of interested academics. List details (filednum, ID and title) of the most popular field together with the total number of interested academics.
