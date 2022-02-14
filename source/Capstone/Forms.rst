Creating the Forms
==================
Now that the basic website has been setup and the database connections have been
established, it's time to work on the full development and functionality of the
website.


New Student Form
----------------
I created the new student form which requires the users to enter the student's
first name, last name, street address, bldg/suite/lot #s (if any), city, state,
zipcode, phone number, and email.

Added the following to the form action as a basic security measure which reads
code tags as plain text, so hopefully hackers have a harder time manipulating
the form and preventing sql injections.

.. code-block:: php

  action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);


