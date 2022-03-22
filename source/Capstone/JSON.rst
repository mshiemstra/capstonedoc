Incorporating JSON
==================

The more modern way to insert data into the databases while validationg the
information is use to JSON.  That allows you to use JavaScript with SQL to insert
or manipulate the data both on the client side, and the server side.  JSON is
used for collecting and sending data over a network connection. It is mostly used
to send data between a server and a web page.

I used JSON on the enroll student form to add existing students to new classes.
To do that, I compared the student ID that was entered in the field to
the database and if the ID exists, the student will be added to the entered class
by class ID.  If the ID entered in the field does NOT match any records, a message
indicating the entered student id was not found and no records will be entered
into the database.

Here are some examples of the updates:

JSON:
.. code-block:: json

       const serialize_form = form => JSON.stringify(
         Array.from(new FormData(form).entries())
         .reduce((m, [ key, value ]) => Object.assign(m, { [key]: value }), {})
     );

     $('#enrollment_form').on('submit', function(e) {
       e.preventDefault();
       const json = serialize_form(this);
       $.ajax({
         type: 'POST',
         url: 'enroll_student_process.php',
         dataType: 'json',
         data: json,
         contentType: 'application/json',
         success: function(data) {
           $('#result').text(data['message']);
           if(data['success']){
             $('#class_id').val("");
             $('#student_id').val("");
           }
         }
       });
     });

PHP:
.. code-block:: php

     $sql = "SELECT * FROM class WHERE class_id = $class_id";
     $result = $conn->query($sql);

     if($result->num_rows == 0) {
	   $message = 'No class record found';
	   echo "{\"message\":\"$message\", \"success\":false}";
	   exit;
     }


     $sql = "SELECT * FROM enrollment WHERE student_id = $student_id AND class_id = $class_id";
     $result = $conn->query($sql);

     if($result->num_rows == 1) {
	   $message = 'Student is already enrolled in that class';
	   echo "{\"message\":\"$message\", \"success\":false}";
	   exit;

     }

     $sql = "INSERT INTO enrollment VALUES ($class_id, $student_id)";

     if (mysqli_query($conn,$sql)) {
       $message = 'Record Added';
     }
     else {
	   $message = "error adding user in database $sql";
     }

     echo "{\"message\":\"$message\", \"success\":true}";
