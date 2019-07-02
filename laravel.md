# Laravel Cheatsheet / Troubleshooting

On github: https://github.com/patopitaluga/patooverflow/blob/master/laravel.md

Also useful:
* [PHP cheatsheet and useful snippets](https://github.com/patopitaluga/patooverflow/blob/master/php.md)

Index:
* [artisan new migration](#artisan-new-migration)
* [Backpack: reorder doesn't work on remote environment](#backpack-reorder-doesnt-work-on-remote-environment)
* [Generate key for the .env file](#generate-key-for-the-env-file)
* [Error: Specified key was too long; max key length is 767 bytes](#error-specified-key-was-too-long)
* [Error: The page has expired due to inactivity](#error-the-page-has-expired-due-to-inactivity)

------
## <a name="artisan-new-migration"></a> artisan new migration

```
php artisan make:migration create_users_table --create=users
```
or

```
php artisan make:migration add_votes_to_users_table --table=users
```

------
## <a name="generate-key-for-the-env-file"></a> Generate key for the .env file

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

------
Ignore the rest code. Is styling for local display of this file using https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk
<style>
  .markdown-body {
    position: relative;
  }
  .cpy-btns {
    background: transparent;
    border: 0;
    cursor: pointer;
    display: block;
    font-family: monospace;
    font-size: 11px;
    margin-top: -4px;
    position: absolute;
    right: 45px;
    width: auto;
  }
  .cpy-btns::before {
    content: 'COPY'
  }
</style>
