Capstone Organization
=====================

One thing I have learned from this project so far is organization is key. When I
first started, I thought I did a decent job by creating folders for the includes
files, the js files, the css files, and the validation files.  Turns out, while
those are great to setup the main page and function of the site, I would need to
add folders to separate students from teachers.

So, I created the new folders, but obviously there was a lot more that needed
to be updated.  Simply moving the files into their respective folders actually
broke the site.  All of the functions and all of the time I spent setting up
the site and the forms were wasted.

However, I already planned for that to happen, so I was able to easily go into
all of the files that were specific for student and update the links and connections
to where everything was working again with minimal effort.

Once I got student updated, I created a new folder for teachers and just copied
all of the files and folders in student and pasted them in the teachers folder.
Since everything was setup for student in the teachers folder, both the student
and teacher pages were identical.

With Sublime-Text, I was able to go into all of the files in the teachers folder,
press CTRL+F and search for every instance where student was listed.  I changed
everything from student to teacher and adjusted the links and connections for
the teachers files and confirmed it's working as well as the students now.

I did have to go into phpMyAdmin to adjust the tables though, because apparently
when I started this project I was planning on including the teacher's home
address along with their office address.  I might still do that if I have time,
but for now I will just list which campus they are at instead of their entire
office address.