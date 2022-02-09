Week 4 Progress (total 10 hours)
================================

Modifying Capstone Docs (10 hours)
-----------------------

Went through the capstone documents and split up `subject/index.rst <C:\xampp\htdocs\hiemstraonlinedesign.com\school-files\simpson\spring_2022\capstonedoc\source\subject\index.rst>`_ into separate
weeks.  Also, added more code examples and better explanations of what was
completed each week.  See below for a few updates made in the previous weeks:

Week 1
------

Created a separate head.php object to use as an include function in the other
pages so any updates to styles or functions only have to be executed once.

I also created a styles.css sheet for the site's styles.

.. code-block:: html+php

      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <meta name="author" content="Matt Hiemstra">

      <title>Grade Book</title>
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
      <link rel="stylesheet" href="https://use.typekit.net/uho4dic.css">
      <link rel="stylesheet" type="text/css" href="css/styles.css">
      <script src="js/functions.js"></script>
      <script src="js/formValidation.js"></script>
      <script src="js/student_regex_restriction.js"></script>
      <?php include 'db.php'; ?>


Week 2
------
Here, I created a capstone db containing a few tables for students, classes, and
teachers.


.. image:: C:\xampp\htdocs\hiemstraonlinedesign.com\school-files\simpson\spring_2022\capstone\images\capstone_database.png

   :width: 400
   :alt: Capstone Database Tables

After creating the database and tables, I created a db.php sheet containing the
following code to connect to the main database:

.. code-block:: php

      <?php
        $servername = "localhost";
        $username = "mshiemstra";
        $password = "June6187!";
        $database = "capstone";

        $conn = mysqli_connect($servername, $username, $password, $database);

        if ($conn->connect_error) {
            die("Connection failed: " . $conn->connect_error);
        }
    ?>

Additionally, I created a new_student.php sheet for the new student form where
the end user will enter the new student's information such as their student id,
name, and address.

.. image:: C:\xampp\htdocs\hiemstraonlinedesign.com\school-files\simpson\spring_2022\capstone\images\student_table.png

   :width: 600
   :alt: Capstone Student Table



Week 3
-----
I added a formHandling.php sheet which contains all of the form security and
validations, and a formValidations.js sheet to assist with initial security
(real time warnings if fields aren't filled out correctly).

A short example of the formHandling.php is:
.. image:: C:\xampp\htdocs\hiemstraonlinedesign.com\school-files\simpson\spring_2022\capstone\images\php_formHandling.png

   :width: 600
   :alt: PHP formHandling example

A short example of the formValidations.js is:
.. code-block:: js

      function student_firstName() {
          let student_fName = document.getElementById("student_fName").value;

          let patt = new RegExp(/^[a-zA-Z -]*$/);
          let res = patt.exec(student_fName);

          if(student_fName == "" || student_fName == null || student_fName == "null" || student_fName == undefined || student_fName == "undefined" || res == null) {

            document.getElementById("error2").innerHTML = "Please enter a valid first name";
            document.getElementById("student_fName").style.border = "1px solid red";
            return validForm = false;
          }
          else {
            document.getElementById("error2").innerHTML = "";
            document.getElementById("student_fName").style.borderTop = "2px solid #BDBDBD";
            document.getElementById("student_fName").style.borderLeft = "1px solid #BDBDBD";
            document.getElementById("student_fName").style.borderBottom = "1px solid #BDBDBD";
            document.getElementById("student_fName").style.borderRight = "1px solid #BDBDBD";

            return validForm = true;
          }
      }