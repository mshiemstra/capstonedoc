Week 1 Progress (total 10 hours)
================================

The Setup (10 hours)
-------------------
I built the basic foundation of the website primarily in HTML5 and CSS.  I used
PHP to include standard sections such as the <head>.  For most of the objects in
the head, there will be no changes, and if there are, those changes will need to
be implemented on all of the other pages in the website.

Another thing I did for the initial setup, was created the different function and
stylesheets that will be imported into the website.  These pages include the
CSS, Javascript, PHP, and database files.

.. code-block:: html
      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <meta name="author" content="Matt Hiemstra">

      <title>Grade Book</title>
      <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
      </script>
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
      <link rel="stylesheet" href="https://use.typekit.net/uho4dic.css">
      <link rel="stylesheet" type="text/css" href="css/styles.css">
      <script src="js/functions.js"></script>
      <script src="js/formValidation.js"></script>
      <script src="js/student_regex_restriction.js"></script>
      <?php include 'db.php'; ?>


