plogger-pdo
=======
A simple php-based web gallery that can be integrated into your website.
This fork uses PDO as the database backend instead of the depreciated mysql library. I've included support for mysql and pgsql out of the box.

Installation & Usage
--------------------
To install, upload all of the files in the Plogger distribution to your web server.
Next, create a SQL database and user from your web hosting control panel or database shell.
Then, run the install script (/plog-admin/_install.php) in the web browser of your choice.
The script will guide you through the rest of the installation process.

Integration
-----------
To integrate Plogger into your website, place the following PHP statements in the .php
file you wish display the gallery in:

First line of the .php file -> ```<?php require("path/to/plogger.php");``` ?>
In the HEAD section -> ```<?php the_plogger_head(); ?>```
In the BODY section where you want the gallery -> ```<?php the_plogger_gallery(); ?>```

Upgrading from -RC1
-------------------
- Edit your DB information and table prefix into /plog-admin/_upgrade.php 
- Navigate to the script in your browser.
- This is a simple one-shot PHP script, so randomly refreshing or running it more than once may result in unpredictable behavior. 
- As with any database schema upgrade, your mileage may vary. I STRONGLY recommend you use mysqldump or similar to make a backup of your database first. 

Differences from -RC1
---------------------
- Database schema has been slightly changed to accomodate my changes to the codebase. If you are coming from RC1, see upgrade information above.
- Upgrade code for revisions older than RC1 has been removed since it would be overly complex and time consuming to update properly.
- Gallery URL handling improved. Install script will detect HTTP/HTTPS, and admin panel will now allow relative paths to be used for the gallery location.
- Certain error messages adapted to PDO changes. Most DB errors will be hidden by default unless PLOGGER_DEBUG is on for security and elegance reasons.
- The phpthumb library has been updated to the latest version (1.7.13) 
- More elegant handling of the EXIF information boxes (hides blank fields, option to turn off display completely). 
- SQL queries have been updated to be a more database agnostic and allow compatibility with both MySQL and PostgreSQL with minimal conditionals. 
- Other minor fixes

Licensing, Support, and other Credits
-------------------------------------
- Original Project: http://www.plogger.org
- Updated fork I used as the basis of mine https://github.com/alexzhuustc/plogger
- phpThumb: http://phpthumb.sourceforge.net/
- My edits are licensed under the same terms as the original project (GPL).
- If you see something wrong or that needs improving, file a bug or submit a pull request. I'll try my best to maintain this, but it's mostly a free-time project.
