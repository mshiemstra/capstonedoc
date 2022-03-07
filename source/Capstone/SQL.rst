Writing SQL Queries
===================

Writing SQL queries are a very important part of web development if you're working
with databases.  Without writing queries, you'd never see the content within the
database.  Writing queries begins with a SELECT statement which identifies which
records you want to view.

You can either select all columns, or specific ones based on the information
you're needing. In many cases, you don't need to view every column in a table
within your database.  The below example is a way to write an SQL query within
the website.

.. code-block:: PHP

     $sql =
     "SELECT C.class_id, C.class_desc, C.class_name, C.class_teacher, C.class_term,
             E.student_id, COUNT(*) AS student_count
     FROM class AS C, enrollment AS E, student AS S
     WHERE E.class_id = C.class_id
     AND E.student_id = S.student_id
     GROUP BY class_id";


The above example is what I used to count the amount of students in each class
listed in the class table.  This is helpful information because each class can
only have a certain amount of students in them.  The output of that query looks
like:

.. image:: classes_screenshot.png
   :width: 600
   :alt: Table showing number of students in each class