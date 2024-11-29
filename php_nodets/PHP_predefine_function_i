PHP provides a wide range of predefined functions that simplify development and make coding more efficient. Below are some of the **important predefined PHP functions** along with their **usage** across various categories:

---

### **1. String Functions**
#### **`strlen()`** - Get String Length
Returns the length of a string.
```php
$string = "Hello World!";
echo strlen($string);  // Outputs: 12
```

#### **`strpos()`** - Find the Position of First Occurrence
Finds the position of the first occurrence of a substring in a string.
```php
echo strpos("Hello world", "world");  // Outputs: 6
```

#### **`str_replace()`** - Replace Substrings
Replaces all occurrences of a string with another string.
```php
echo str_replace("world", "PHP", "Hello world!");  // Outputs: Hello PHP!
```

#### **`substr()`** - Extract a Part of a String
Returns part of a string starting at a given position.
```php
echo substr("Hello world!", 6, 5);  // Outputs: world
```

#### **`trim()`** - Strip Whitespace
Removes whitespace or other characters from the beginning and end of a string.
```php
$string = "   Hello world!  ";
echo trim($string);  // Outputs: Hello world!
```

---

### **2. Array Functions**
#### **`array_merge()`** - Merge Arrays
Merges one or more arrays into one.
```php
$array1 = [1, 2];
$array2 = [3, 4];
$result = array_merge($array1, $array2);  // [1, 2, 3, 4]
```

#### **`array_push()`** - Push to an Array
Adds one or more elements to the end of an array.
```php
$stack = ["apple", "banana"];
array_push($stack, "orange");
print_r($stack);  // Outputs: Array ( [0] => apple [1] => banana [2] => orange )
```

#### **`array_pop()`** - Pop from an Array
Removes and returns the last element from an array.
```php
$stack = ["apple", "banana", "orange"];
array_pop($stack);  // Outputs: orange
```

#### **`in_array()`** - Check if Value Exists in Array
Checks if a value exists in an array.
```php
$fruits = ["apple", "banana", "orange"];
echo in_array("banana", $fruits);  // Outputs: 1 (true)
```

#### **`array_filter()`** - Filter Array Elements
Filters elements of an array using a callback function.
```php
$numbers = [1, 2, 3, 4, 5];
$even = array_filter($numbers, fn($n) => $n % 2 == 0);
print_r($even);  // Outputs: Array ( [1] => 2 [3] => 4 )
```

---

### **3. Date and Time Functions**
#### **`date()`** - Format a Date
Formats a local date and time.
```php
echo date("Y-m-d H:i:s");  // Outputs: 2024-10-03 14:55:32 (for example)
```

#### **`time()`** - Get Current Unix Timestamp
Returns the current Unix timestamp.
```php
echo time();  // Outputs: 1696382132 (Unix timestamp)
```

#### **`strtotime()`** - Parse a Date String
Parses an English textual datetime into a Unix timestamp.
```php
$timestamp = strtotime("next Monday");
echo date("Y-m-d", $timestamp);  // Outputs: 2024-10-07 (for example)
```

---

### **4. File System Functions**
#### **`file_get_contents()`** - Read File into a String
Reads the entire file content into a string.
```php
$content = file_get_contents("example.txt");
echo $content;
```

#### **`file_put_contents()`** - Write a String to a File
Writes data to a file.
```php
file_put_contents("example.txt", "Hello, world!");
```

#### **`fopen()` / `fclose()`** - Open/Close a File
Opens a file and returns a file pointer resource.
```php
$handle = fopen("example.txt", "r");
fclose($handle);
```

#### **`unlink()`** - Delete a File
Deletes a file.
```php
unlink("example.txt");
```

---

### **5. Math Functions**
#### **`rand()`** - Generate a Random Number
Generates a random integer.
```php
echo rand(1, 100);  // Outputs: A random number between 1 and 100
```

#### **`ceil()`** - Round Up a Floating Point Number
Rounds a number up to the nearest integer.
```php
echo ceil(4.3);  // Outputs: 5
```

#### **`floor()`** - Round Down a Floating Point Number
Rounds a number down to the nearest integer.
```php
echo floor(4.7);  // Outputs: 4
```

#### **`abs()`** - Absolute Value
Returns the absolute value of a number.
```php
echo abs(-10);  // Outputs: 10
```

---

### **6. JSON Functions**
#### **`json_encode()`** - Encode Data to JSON Format
Encodes a PHP value into a JSON string.
```php
$data = ["name" => "John", "age" => 30];
echo json_encode($data);  // Outputs: {"name":"John","age":30}
```

#### **`json_decode()`** - Decode JSON Data
Decodes a JSON string into a PHP variable.
```php
$json = '{"name":"John","age":30}';
$data = json_decode($json, true);
print_r($data);  // Outputs: Array ( [name] => John [age] => 30 )
```

---

### **7. Error Handling and Debugging Functions**
#### **`error_reporting()`** - Set Error Reporting Level
Controls which errors are shown by PHP.
```php
error_reporting(E_ALL);  // Show all errors and warnings
```

#### **`var_dump()`** - Dump Variable Information
Dumps information about a variable, including its type and value.
```php
$var = ["apple", "banana"];
var_dump($var);  // Outputs detailed information about the array
```

#### **`print_r()`** - Print Human-readable Information
Outputs human-readable information about a variable.
```php
print_r($var);  // Outputs: Array ( [0] => apple [1] => banana )
```

---

### **8. Session Functions**
#### **`session_start()`** - Start a Session
Starts a new session or resumes an existing session.
```php
session_start();
$_SESSION['user'] = 'John';
```

#### **`session_destroy()`** - Destroy a Session
Destroys all data registered to a session.
```php
session_start();
session_destroy();  // Ends the current session and deletes session data
```

---

### **9. HTTP and Server Variables**
#### **`header()`** - Send Raw HTTP Headers
Sends a raw HTTP header to the client.
```php
header("Location: http://example.com");  // Redirects to example.com
```

#### **`$_GET` and `$_POST`** - Retrieve GET/POST Data
Fetches data sent via HTTP GET or POST methods.
```php
echo $_GET['id'];  // Retrieves a parameter from the URL like ?id=123
echo $_POST['name'];  // Retrieves data from a submitted form
```

#### **`$_SERVER`** - Get Server Information
Returns information about the server environment.
```php
echo $_SERVER['HTTP_USER_AGENT'];  // Outputs the browser's user agent string
```

---

### **10. Miscellaneous Functions**
#### **`define()`** - Define a Constant
Defines a constant that cannot be changed.
```php
define("SITE_NAME", "My Website");
echo SITE_NAME;  // Outputs: My Website
```

#### **`isset()`** - Check if a Variable is Set
Determines if a variable is set and is not `null`.
```php
$var = "Hello";
echo isset($var);  // Outputs: 1 (true)
```

#### **`empty()`** - Check if a Variable is Empty
Checks whether a variable is empty (zero, `null`, or an empty string).
```php
$var = "";
echo empty($var);  // Outputs: 1 (true)
```

#### **`die()` / `exit()`** - Terminate the Script
Stops the execution of a script and optionally outputs a message.
```php
die("Script terminated");  // Stops execution and outputs "Script terminated"
```

---

These functions are among the most commonly used in PHP for handling strings, arrays, dates, files, sessions, error handling, and more. Familiarizing yourself with these will improve your efficiency and understanding as a PHP developer. Let me know if you'd like details on any specific function or category! 




Here are **more predefined PHP functions** across different categories, covering security, database interaction, file handling, and other utility functions that are useful for advanced PHP development.

---

### **11. Security Functions**
#### **`htmlspecialchars()`** - Prevent XSS Attacks
Converts special characters to HTML entities to prevent cross-site scripting (XSS).
```php
$user_input = "<script>alert('Hello!');</script>";
echo htmlspecialchars($user_input);  
// Outputs: &lt;script&gt;alert('Hello!');&lt;/script&gt;
```

#### **`md5()`** - Generate MD5 Hash
Generates a hash value using the MD5 algorithm. **Note:** It's not recommended for passwords due to vulnerabilities.
```php
echo md5("password123");  // Outputs: 482c811da5d5b4bc6d497ffa98491e38
```

#### **`password_hash()`** - Hash a Password (Secure)
Hashes a password securely using `bcrypt`.
```php
$hash = password_hash("password123", PASSWORD_DEFAULT);
echo $hash;  // Outputs a secure hash
```

#### **`password_verify()`** - Verify a Password
Verifies a password against a hash created by `password_hash()`.
```php
if (password_verify("password123", $hash)) {
    echo "Password is valid!";
}
```

#### **`filter_var()`** - Sanitize/Validate Data
Filters a variable with a specified filter, such as sanitizing a string or validating an email address.
```php
$email = "someone@example.com";
if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Valid email!";
}
```

---

### **12. Database Functions (MySQLi)**
#### **`mysqli_connect()`** - Connect to MySQL Database
Establishes a connection to a MySQL database using MySQLi.
```php
$connection = mysqli_connect("localhost", "root", "", "database");
if (!$connection) {
    die("Connection failed: " . mysqli_connect_error());
}
```

#### **`mysqli_query()`** - Execute SQL Query
Executes an SQL query on a MySQL database.
```php
$result = mysqli_query($connection, "SELECT * FROM users");
```

#### **`mysqli_fetch_assoc()`** - Fetch a Row as an Associative Array
Fetches a result row as an associative array.
```php
while ($row = mysqli_fetch_assoc($result)) {
    echo $row['name'];
}
```

#### **`mysqli_close()`** - Close Database Connection
Closes an open database connection.
```php
mysqli_close($connection);
```

---

### **13. File Upload Functions**
#### **`move_uploaded_file()`** - Move an Uploaded File
Moves an uploaded file to a new location on the server.
```php
if (move_uploaded_file($_FILES['file']['tmp_name'], "uploads/" . $_FILES['file']['name'])) {
    echo "File uploaded successfully!";
}
```

#### **`is_uploaded_file()`** - Check if a File is Uploaded via HTTP POST
Checks whether a file is uploaded via HTTP POST.
```php
if (is_uploaded_file($_FILES['file']['tmp_name'])) {
    echo "File uploaded!";
}
```

#### **`filesize()`** - Get File Size
Returns the size of a file in bytes.
```php
echo filesize("example.txt");  // Outputs file size in bytes
```

---

### **14. File Handling Functions**
#### **`fwrite()`** - Write to a File
Writes a string to a file (opened with `fopen()`).
```php
$handle = fopen("example.txt", "w");
fwrite($handle, "Hello, world!");
fclose($handle);
```

#### **`fread()`** - Read from a File
Reads a specified number of bytes from a file.
```php
$handle = fopen("example.txt", "r");
$content = fread($handle, filesize("example.txt"));
fclose($handle);
echo $content;
```

#### **`copy()`** - Copy a File
Copies a file to another location.
```php
copy("source.txt", "destination.txt");
```

---

### **15. Session and Cookie Functions**
#### **`setcookie()`** - Set a Cookie
Sets a cookie that will be sent to the browser.
```php
setcookie("user", "John", time() + 3600);  // Set cookie valid for 1 hour
```

#### **`$_COOKIE`** - Retrieve Cookie Values
Accesses the value of a cookie set by the server.
```php
echo $_COOKIE['user'];  // Outputs: John (if the cookie was set)
```

#### **`session_set_cookie_params()`** - Set Session Cookie Parameters
Set the parameters for the session cookie.
```php
session_set_cookie_params(3600);  // Sets session cookie to expire in 1 hour
session_start();
```

---

### **16. Regular Expression Functions**
#### **`preg_match()`** - Perform a Regular Expression Match
Performs a match using a regular expression.
```php
if (preg_match("/\d+/", "123abc")) {
    echo "Found a number!";
}
```

#### **`preg_replace()`** - Replace Text Using a Regular Expression
Replaces occurrences of a regular expression in a string.
```php
$text = "I have 3 apples and 5 oranges.";
$new_text = preg_replace("/\d+/", "many", $text);
echo $new_text;  // Outputs: I have many apples and many oranges.
```

---

### **17. Error Handling Functions**
#### **`trigger_error()`** - Generate a User-Level Error/Warn/Notice
Generates a user-level error/warning/notice.
```php
if ($something_is_wrong) {
    trigger_error("An error occurred!", E_USER_ERROR);
}
```

#### **`set_error_handler()`** - Custom Error Handler
Sets a user-defined function to handle errors.
```php
function customError($errno, $errstr) {
    echo "Error: [$errno] $errstr";
}
set_error_handler("customError");
```

#### **`restore_error_handler()`** - Restore Previous Error Handler
Restores the previous error handler that was active before `set_error_handler()` was called.
```php
restore_error_handler();
```

---

### **18. JSON Functions (Advanced)**
#### **`json_last_error()`** - Get the Last JSON Error
Returns the last error occurred during JSON encoding/decoding.
```php
$data = json_decode("{'invalid_json':}");
if (json_last_error() != JSON_ERROR_NONE) {
    echo "JSON Error: " . json_last_error_msg();
}
```

#### **`json_last_error_msg()`** - Get a Textual JSON Error Message
Returns the error message for the last JSON error.
```php
$data = json_decode("{'invalid_json':}");
echo json_last_error_msg();  // Outputs: Syntax error
```

---

### **19. XML Parsing Functions**
#### **`simplexml_load_string()`** - Load XML from a String
Loads an XML string into an object.
```php
$xml_string = "<note><to>Tove</to><from>Jani</from></note>";
$xml = simplexml_load_string($xml_string);
echo $xml->to;  // Outputs: Tove
```

#### **`simplexml_load_file()`** - Load XML from a File
Loads an XML file into an object.
```php
$xml = simplexml_load_file("example.xml");
echo $xml->to;
```

#### **`xml_parse()`** - Parse XML Data
Parses XML data using an XML parser.
```php
$xml_parser = xml_parser_create();
xml_parse($xml_parser, "<root><child>data</child></root>");
xml_parser_free($xml_parser);
```

---

### **20. Networking Functions**
#### **`gethostbyname()`** - Get Hostname's IP Address
Resolves a hostname into an IP address.
```php
$ip = gethostbyname("www.example.com");
echo $ip;  // Outputs: 93.184.216.34 (for example)
```

#### **`fsockopen()`** - Open Internet or Unix Domain Socket Connection
Establishes a socket connection.
```php
$fp = fsockopen("www.example.com", 80);
fwrite($fp, "GET / HTTP/1.1\r\nHost: www.example.com\r\n\r\n");
fclose($fp);
```

---

### **21. URL Functions**
#### **`parse_url()`** - Parse a URL into Components
Parses a URL and returns its components.
```php
$url = "http://example.com?name=John&age=30";
print_r(parse_url($url));  // Outputs an array with scheme, host, query, etc.
```

#### **`http_build_query()`** - Build a Query String
Generates a URL-encoded query string.
```php
$params = ['name' => 'John', 'age' => 30];
$query_string = http_build_query($params);
echo $query_string;  // Outputs: name=John&age=30
```

---

These additional functions expand the versatility of PHP, enabling you to work with a wide range of operations such as error handling, regular expressions, networking, and more. Let me know if you'd like further details on any specific function!







