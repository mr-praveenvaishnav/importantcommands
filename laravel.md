composer create-project --prefer-dist laravel/zanzeomultivendor

composer global require laravel/installer
laravel --version

create new project 

 //laravel new project-name

change port 

//php artisan serve --port=8002


composer require tymon/jwt-auth 
php artisan config:clear
php artisan jwt:secret


composer dump-autoload

1. **Create a New Laravel Project:**
   composer create-project --prefer-dist laravel/laravel project-name
  
   php artisan serve

  

3. **Create a Controller:**
   php artisan make:controller MyController
   ```
 4. **Create a Model:**
   php artisan make:model MyModel
   ```
 5. **Create a Migration:**
   php artisan make:migration create_table_name
 6. **Run Migrations:**
   php artisan migrate
 7. **Create a Middleware:**
   php artisan make:middleware MyMiddleware
  8. **Generate Key for .env:**

   php artisan key:generate

    Sets the application key in the .env file.

9. **Create a Resource Controller:**
   php artisan make:controller MyController --resource
   ```
   Generates a resource controller with CRUD methods.

10. **Clear Caches:**
    ```bash
    php artisan cache:clear
    php artisan config:clear
    php artisan view:clear
    ```
    Clears various cached data.

11. **List All Artisan Commands:**
    ```bash
    php artisan list
    ```
    Displays a list of all available Artisan commands.

These commands are just a subset of the functionality provided by Laravel's Artisan CLI. You can explore more commands and their options by referring to the official Laravel documentation or using the `php artisan list` command.



$contact_form = WPCF7_ContactForm::get_current();
$contact_form_id = $contact_form -> id; 



# laravel  benifit 
open source 
MNV arcitrature 
ELegant systax 
db migration ,  ORM , -- realtion query in complex  
Robust Routing system  , ( SEO base url , )
 Commant line interface  ( composer  )
pawoerfull Template engin - > blade template 
authentication , and authorization ( inblid )
testing and debuuging 
secturity (xss , Csrf , SQL Incation )
word Scalbity and performance ( Redis and memcached ) ( invblid )
Robust ecosystem and communtinty 


$student = DB::table('student' );
$test = DB:table('test')
            ->union($student) get(); 




Step 1: Create Multiple User Models:

 <code>

php artisan make:model User
php artisan make:model Admin

</code>


<b>Step 2: Configure Authentication Guards: </b>


<code>
    'guards' => [
    'web' => [
        'driver' => 'session',
        'provider' => 'users',
    ],

    'admin' => [
        'driver' => 'session',
        'provider' => 'admins',
    ],
],

</code>.

<b>Step 3: Define Authentication Providers: </b>

<code>
    'providers' => [
    'users' => [
        'driver' => 'eloquent',
        'model' => App\Models\User::class,
    ],

    'admins' => [
        'driver' => 'eloquent',
        'model' => App\Models\Admin::class,
    ],
],
</code>

<b>
    Step 4: Implement Authentication Logic:

</b>

