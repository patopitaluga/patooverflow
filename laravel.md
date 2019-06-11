# Laravel Cheatsheet / Troubleshooting

Index:
* [Error: The page has expired due to inactivity](#error-the-page-has-expired-due-to-inactivity)

------

## <a name="error-the-page-has-expired-due-to-inactivity"></a> Error: The page has expired due to inactivity
Might be because the post form is missing the CSRF Token
```
<input type="hidden" name="_token" value="{{ csrf_token() }}"/>
```
Or SESSION_SECURE_COOKIE might be set to true when https is not possible (local environment) in config/session.php. You can set it as SESSION_SECURE_COOKIE=false in the .env file in your local environment.
