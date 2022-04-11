Tables
======

Most, if not all websites use a variety of tables.  Some are more formal amd
use the <table> object, and others use a series of divs to have more freedom with
styles.  You could build a custom table where you create all of the table elements
yourself, or you could use one of any number of CMS tables like WordPress, Bootstrap,
or Foundation, etc.

Using Custom Tables
-------------------

When I first built the site, I decided to create my own tables using my own table
elements.  I figured that way I could collect and/or display user information in
a way I wanted to, which would more or less match the them of the rest of the site.
I would use the formal table elements and in the CSS, style it however I waned.

While that method worked, they all ran off of the screen so I had to add an

.. code-block:: CSS
    overflow:scroll;

style, so the user could scroll to the end of the table without moving the entire
page itself. This worked well, but I admit it looks pretty tacky, but I assumed
that's just because the was a lot of information I needed to display.

Bootstrap Table
---------------

After discussing this with Paul Craven, he suggested I take a look at the Bootstrap
tables.  After reviewing them, I discovered there were several that would display
all of the information I had gathered and display it in a table that did NOT run
off of the screen.  It also looked cleaner and easier to see what each piece of
information the the table was displaying.

Converting all of the tables in the site was actually quite a bit easier.  Of course
I had to add the script source and links to reach the Bootstrap functions and
styles, but after doing that, just add the classes "table" and "table-bordered"
to the table element; that's it.  Doing that converted my custom tables into more
professional and cleaner looking tables that were easier to read.

.. code-block:: HTML
    <table class="table table-bordered">

