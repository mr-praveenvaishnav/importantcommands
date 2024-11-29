Here are **more advanced and typical PHP predefined functions** that are often used in complex, real-world applications:

---

### **22. Advanced Array Functions**

#### **`array_walk()`** - Apply a Callback Function to an Array
Applies a user-defined function to each element of an array.
```php
$numbers = [1, 2, 3, 4];
array_walk($numbers, function(&$val, $key) {
    $val *= 2;  // Multiply each element by 2
});
print_r($numbers);  // Outputs: [2, 4, 6, 8]
```

#### **`array_reduce()`** - Reduce an Array to a Single Value
Iteratively reduces the array to a single value using a callback function.
```php
$sum = array_reduce([1, 2, 3, 4], function($carry, $item) {
    return $carry + $item;  // Summing all values
});
echo $sum;  // Outputs: 10
```

#### **`array_filter()`** - Filter Elements of an Array
Filters an array based on a user-defined condition.
```php
$numbers = [1, 2, 3, 4, 5];
$even_numbers = array_filter($numbers, function($num) {
    return $num % 2 == 0;  // Only even numbers
});
print_r($even_numbers);  // Outputs: [2, 4]
```

#### **`array_intersect()`** - Find Common Elements in Arrays
Returns an array containing elements present in all input arrays.
```php
$array1 = [1, 2, 3, 4];
$array2 = [3, 4, 5, 6];
$common = array_intersect($array1, $array2);
print_r($common);  // Outputs: [3, 4]
```

#### **`array_merge()`** - Merge One or More Arrays
Merges the elements of one or more arrays into a single array.
```php
$array1 = [1, 2];
$array2 = [3, 4];
$merged = array_merge($array1, $array2);
print_r($merged);  // Outputs: [1, 2, 3, 4]
```

---

### **23. Object-Oriented Programming (OOP) Functions**

#### **`get_class()`** - Get the Class Name of an Object
Returns the class name of the object.
```php
class User {}
$user = new User();
echo get_class($user);  // Outputs: User
```

#### **`method_exists()`** - Check if a Class Method Exists
Checks whether a method is defined in a class.
```php
class User {
    public function sayHello() {
        return "Hello!";
    }
}
$user = new User();
if (method_exists($user, 'sayHello')) {
    echo $user->sayHello();  // Outputs: Hello!
}
```

#### **`property_exists()`** - Check if a Class Property Exists
Determines if a class property exists.
```php
class User {
    public $name;
}
$user = new User();
if (property_exists($user, 'name')) {
    echo "Property exists!";
}
```

#### **`call_user_func()`** - Call a Callback Function
Calls a user-defined callback function with specified parameters.
```php
function greet($name) {
    return "Hello, $name!";
}
echo call_user_func('greet', 'John');  // Outputs: Hello, John!
```

#### **`class_exists()`** - Check if a Class Exists
Verifies whether a class has been defined.
```php
if (class_exists('User')) {
    echo "Class User exists!";
}
```

---

### **24. JSON Functions**

#### **`json_encode()`** - Encode Data into JSON Format
Encodes a PHP array or object into a JSON string.
```php
$data = ['name' => 'John', 'age' => 30];
echo json_encode($data);  // Outputs: {"name":"John","age":30}
```

#### **`json_decode()`** - Decode JSON String into PHP Data
Decodes a JSON string into a PHP array or object.
```php
$json = '{"name":"John","age":30}';
$data = json_decode($json, true);  // Pass true to return as array
print_r($data);  // Outputs: Array ( [name] => John [age] => 30 )
```

---

### **25. String Handling Functions (Advanced)**

#### **`str_replace()`** - Replace Substring in a String
Replaces all occurrences of the search string with the replacement string.
```php
$text = "I have apples.";
$new_text = str_replace("apples", "oranges", $text);
echo $new_text;  // Outputs: I have oranges.
```

#### **`str_split()`** - Convert a String to an Array
Splits a string into an array of characters or into chunks of a specified length.
```php
$string = "Hello";
$array = str_split($string, 2);  // Splits into chunks of 2
print_r($array);  // Outputs: Array ( [0] => He [1] => ll [2] => o )
```

#### **`trim()`** - Strip Whitespace (or Other Characters) from the Start and End of a String
Removes whitespace or other predefined characters from the start and end of a string.
```php
$string = "  Hello World  ";
echo trim($string);  // Outputs: "Hello World"
```

#### **`sprintf()`** - Return a Formatted String
Returns a formatted string using placeholders.
```php
$name = "John";
$age = 25;
echo sprintf("My name is %s and I am %d years old.", $name, $age);
// Outputs: My name is John and I am 25 years old.
```

#### **`implode()`** - Join Array Elements into a String
Joins the elements of an array into a single string with a delimiter.
```php
$array = ['apple', 'banana', 'cherry'];
$string = implode(", ", $array);
echo $string;  // Outputs: apple, banana, cherry
```

---

### **26. System and Environment Functions**

#### **`phpinfo()`** - Display PHP Configuration Information
Outputs detailed information about PHP's configuration.
```php
phpinfo();  // Outputs a lot of system information about PHP
```

#### **`ini_get()`** - Get the Value of a PHP Configuration Option
Gets the value of a specific configuration option.
```php
$max_upload_size = ini_get('upload_max_filesize');
echo $max_upload_size;  // Outputs: 2M (or other value)
```

#### **`ini_set()`** - Set the Value of a PHP Configuration Option
Sets the value of a specific configuration option at runtime.
```php
ini_set('display_errors', 1);  // Enables error display
```

#### **`getenv()`** - Retrieve the Value of an Environment Variable
Fetches the value of a specific environment variable.
```php
$path = getenv('PATH');
echo $path;  // Outputs the system's PATH environment variable
```

---

### **27. Output Buffering Functions**

#### **`ob_start()`** - Start Output Buffering
Starts output buffering so that output isn't sent to the browser immediately.
```php
ob_start();  // Start output buffering
echo "Hello World";
$output = ob_get_clean();  // Retrieve buffered output and clean the buffer
echo strtoupper($output);  // Outputs: HELLO WORLD
```

#### **`ob_end_flush()`** - Flush (Send) the Output Buffer and Turn Off Buffering
Flushes the output buffer and sends it to the browser.
```php
ob_start();
echo "This will be flushed to the browser.";
ob_end_flush();  // Flushes the buffer to the browser
```

---

### **28. Advanced File Handling**

#### **`fgetcsv()`** - Read CSV File and Parse Fields
Reads a line from an open file and parses it as CSV fields.
```php
$handle = fopen("data.csv", "r");
while (($data = fgetcsv($handle, 1000, ",")) !== FALSE) {
    print_r($data);  // Outputs each line as an array
}
fclose($handle);
```

#### **`fputs()`** - Write to a File
Writes a string to a file.
```php
$handle = fopen("output.txt", "w");
fputs($handle, "This is a test");
fclose($handle);
```

---

### **29. Date and Time Functions**

#### **`date()`** - Format a Local Date/Time
Formats a local date/time based on a specified format.
```php
echo date("Y-m-d H:i:s");  // Outputs current date and time
```

#### **`strtotime()`** - Parse an English Text Date/Time into a Unix Timestamp
Converts an English textual datetime into a Unix timestamp.
```php
$time = strtotime("next Monday");
echo date("Y-m-d", $time);  // Outputs: Date of next Monday
```

#### **`time()`** - Get Current Unix Timestamp
Returns the current Unix timestamp (seconds since 1970).
```php
echo time();  // Outputs: 1634162873 (or similar)
```

#### **`mktime()`** - Get Unix Timestamp for a Date
Returns the Unix timestamp corresponding to the given date.
```php
echo mktime(0, 0, 0, 12, 25, 2021);  // Outputs: Unix timestamp for December 25, 2021