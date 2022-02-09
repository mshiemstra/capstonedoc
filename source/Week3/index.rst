Capstone Development - Part 2 (total 10 hours)
==============================================
Now that the basic website has been setup and the database connections have been
established, it's time to work on the full development and functionality of the
website.  The overall function of the website is to allow the entry of new
students and teachers into the capstone database and have a relationship with
each other where the user will be able to see which term a specific class is in,
who the teacher of the class is, how many students are in the class, and what
the names and IDs are for each of the students in the class.

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

.. code-block:: php
  action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);


Form Validation and Security (8 hours)
--------------------------------------
Added form validations to the Student Table, checking to ensure each field is
filled out correctly and in the correct formats.  Below is an example of using
regular expressions to verify a value has been entered in the input box, and
only letters and whitespaces are entered in the First Name field.

.. code-block:: PHP
        if (empty($_POST["student_fName"])){
			$student_fName_error = "Student's first name is required";
		}
        else {
			$student_fName = student_input($_POST["student_fName"]);
		   		if (!preg_match("/^[a-zA-Z-' ]*$/",$student_fName)) {
		      	$student_fName_error = "Only letters and white space allowed";
			}
		}