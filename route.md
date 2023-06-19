## Table of Contents

1. [Beginner Tips](#beginner-tips)
2. [Intermediate Tips](#intermediate-tips)
3. [Senior Tips](#senior-tips)

## Beginner Tips 

1. **HTTP methods** 
- you can register a route that responds to multiple HTTP methods using Route::match.
```php
Route::match(['get', 'post'], '/', function () {
    // ...
});
 ```

- you can register a route that responds to all HTTP methods using Route::any.
```php
Route::any('/', function () {
    // ...
});
 ```

2. **Broken Routes** 
- use Route::fallback to handle requests that do not match any defined routes in your application.
```php
Route::fallback(function () {
    return view('errors.404');
});
 ```


## Intermediate Tips 

1. **Subdomain Routes** 
- you can access and check Subdomain by Route::domain.
```php
Route::domain('{account}.localhost')->group(function () {
    Route::get('/', function (string $account) {
        return $account;
    });
});
 ```
