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
