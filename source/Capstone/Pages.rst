Creating the Student Pages
=========================

Now that the database and tables have been setup, the SQL connection has been
established, the form handling and validations have been setup and are working,
and the JSON has been added, it's time to discuss how it all fits together in each
of the pages on the site.

Student Page
------------

On the student.php page, I created a new student form which allows you to add new
students to the database.  The student_formValidations.js and student_formHandling.php
Check the user's input and restricts their data entry so there are no special
characters, and the fields like the student id and their zipcode which require
only numeric values, only accept numeric values and no alpha characters.  The
same is true for the fields that only require alpha characters; no numeric values
will be accepted.

The students.php page shows a list of all of the students in the database under
the student table in the database.  On the page, the user has the option to select
an existing student, to delete a student, or to add a new student.

If the user decides to add a new student, they will click on "Add Student" and
they will be directed to the new student form listed above.  If they click on
"select" next to the existing student's name, they will be directed to a page
which displays all of the classes that student is enrolled in. If they click
"Delete", the student will be deleted from the database.

If the use clicked "Select" next to the student's name, the page they are directed
to has a button which allows them to enroll the student in more classes.  If the
student is already enrolled in the class, the user will receive a message stating
that.

The next step for the student pages, is to include the student's grade next to
each of the classes the student is enrolled in.

Teacher Page
------------

The Teacher page is very similar to the Student page, except instead of listing
the students in the student table, it lists the teachers in the teacher table.
Additionally, if the user clicks "Select" next to the teacher, they will be directed
to a page that lists all of the classes the teacher is teaching; though this page
has not been setup up yet.

Once they page HAS been setup, there will be a button to click to select a class
the teacher is teaching, which will direct the user to a page that lists all of
the students enrolled in that class and the grade each of the students have.
