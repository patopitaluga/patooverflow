# Laravel Cheatsheet / Troubleshooting

Index:
* [artisan new migration](#artisan-new-migration)
* [Backpack: reorder doesn't work on remote environment](#backpack-reorder-doesnt-work-on-remote-environment)
* [Generate key for the .env file](#generate-key-for-the-env-file)
* [Error: Specified key was too long; max key length is 767 bytes](#error-specified-key-was-too-long)
* [Error: The page has expired due to inactivity](#error-the-page-has-expired-due-to-inactivity)

------
## <a name="artisan-new-migration"></a> artisan new migration

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');">Copy to clipboard</button>
```
php artisan make:migration create_users_table --create=users
```
or

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');">Copy to clipboard</button>
```
php artisan make:migration add_votes_to_users_table --table=users
```

------
## <a name="generate-key-for-the-env-file"></a> Generate key for the .env file

<button onclick="var t=document.createElement('textarea');t.style.width='0';t.style.height='0';t.style.border='0';t.value=this.parentElement.nextElementSibling.innerText;document.body.appendChild(t);t.select();document.execCommand('copy');">Copy to clipboard</button>
```
php artisan key:generate
```

------
## <a name="backpack-reorder-doesnt-work-on-remote-environment"></a> Backpack: reorder doesn't work on remote environment
The ajax function has hardcoded "http". To fix it set a custom template for the reorder view writing $this->crud->setReorderView('admin-custom/reorder'); in the setup function in the crud controller file. And copy the file reorder.blade.php from the vendor backpack folder to /resources/views/admin-custom and change the line
```
url: '<?=str_replace('http://', '//', Request::url())?>'
```
in the $.ajax function.

------
## <a name="error-specified-key-was-too-long"></a> Error: Specified key was too long; max key length is 767 bytes
Edit app/Providers/AppServiceProvider.php. Add
```
Schema::defaultStringLength(191);
```
To boot function.

------
## <a name="error-the-page-has-expired-due-to-inactivity"></a> Error: The page has expired due to inactivity
Might be because the post form is missing the CSRF Token
```
<input type="hidden" name="_token" value="{{ csrf_token() }}"/>
```
Or SESSION_SECURE_COOKIE might be set to true when https is not possible (local environment) in config/session.php. You can set it as SESSION_SECURE_COOKIE=false in the .env file in your local environment.
