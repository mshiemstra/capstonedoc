Capstone Introduction (total: 10 hours)
=======================================

For my capstone project, I will be building a fully functional website displaying
some of the classes Simpson is offering, what term those classes are in, who
the teacher of the classes are, the number and names of all the students
attending each of those classes, and finally, the grades each student has in
the class.

The Setup (3 hours)
-------------------
I built the basic foundation of the website primarily in HTML5 and CSS.  I used
PHP to include standard sections such as the <head>.  For most of the objects in
the head, there will be no changes, and if there are, those changes will need to
be implemented on all of the other pages in the website.

Another thing I did for the initial setup, was created the different function and
stylesheets that will be imported into the website.  These pages include the
CSS, Javascript, PHP, and database files.


The Database (7 hours)
----------------------
In order for the end user to pull the information they may need, whether it's a
teacher wanting to see their students and the grades, or the student wanting
to see what class their enrolled in, a database is needed to collect that
information.

The database will have several tables in it to collect each piece of information
to be displayed on the site.  There is a table to collect each of the following:

1. Student

2. Teacher

3. Term

4. Class

5. Grade

Capstone Development - Part 1 (total 10 hours)
==============================================
Now that the basic website has been setup and the database connections have been
established, it's time to work on the full development and functionality of the
website.  This includes setting up the New Student page to allow the end user to
enter new records into the student table and display them on the Students page of
the website.  There are several other forms that will allow new records to be
entered and have those records displayed on the corresponding pages throughout
the website.


Database Setup (7 hours)
------------------------
After building the capstone database, I started with creating the student table
which will allow student records to be inserted.

Website Setup (3 hours)
-----------------------
Connected the website to the database and confirmed the Students page reflects
the records entered in the student table.

Capstone Development - Part 2 (total 10 hours)
==============================================
The overall function of the website is to allow the entry of new students and
teachers into the capstone database and have a relationship with each other
where the user will be able to see which term a specific class is in, who the
teacher of the class is, how many students are in the class, and what the names
and IDs are for each of the students in the class.

Additionally, the user will also be able to see the total information for each
student (ex. name, address, phone number, and email) as well as being able to
view the total information for the teachers as well.


Creating New Student form with basic security (2 Hour)
------------------------------------------------------
Created the new student form which requires the users to enter the student's
first name, last name, street address, bldg/suite/lot #s (if any), city, state,
zipcode, phone number, and email.

Added the following to the form action as a basic security measure which reads
code tags as plain text, so hopefully hackers have a harder time manipulating
the form and preventing sql injections.

..code-block:: PHP
  action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);


Form Validation and Security (8 hours)
--------------------------------------
Added form validations to the Student Table, checking to ensure each field is
filled out correctly and in the correct formats.  Below is an example of using
regular expressions to verify a value has been entered in the input box, and
only letters and whitespaces are entered in the First Name field.

..code-block:: SQL
        if (empty($_POST["student_fName"])){
			$student_fName_error = "Student's first name is required";
		}
        else {
			$student_fName = student_input($_POST["student_fName"]);
		   		if (!preg_match("/^[a-zA-Z-' ]*$/",$student_fName)) {
		      	$student_fName_error = "Only letters and white space allowed";
			}
		}