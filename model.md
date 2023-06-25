## Table of Contents

1. [Beginner Tips](#beginner-tips)
2. [Intermediate Tips](#intermediate-tips)
3. [Senior Tips](#senior-tips)

## Beginner Tips 

1. **Create Method** 
- before using the create method, you will need to specify either a fillable or guarded property on your model class.
- When you define protected $fillable in your model, you specify a list of attributes that are allowed to be mass assigned.
```php
class User extends Model
{
    protected $fillable = ['name', 'email', 'password'];
}
 ```

- When you define protected $guarded in your model, you specify a list of attributes that are not allowed to be mass assigned.
```php
class Product extends Model
{
    protected $guarded = ['id', 'created_at', 'updated_at'];
}
 ```

## Intermediate Tips 

1. **SoftDeletes** 
- SoftDeletes is a feature in Laravel that allows you to mark records as deleted without permanently removing them from the database. 
```php
class Product extends Model
{
    use SoftDeletes;
}
 ```

- 1) Soft Deleting a Record: 
```php
$product = Product::find(1);
$product->delete();
 ```
- 2) Retrieving Soft Deleted Records:
```php
$products = Product::withTrashed()->get();

 ```
- 3) Restoring a Soft Deleted Record:
```php
$product = Product::withTrashed()->find(1);
$product->restore();
 ```

- 4) Permanently Deleting a Soft Deleted Record:
```php
$product = Product::withTrashed()->find(1);
$product->forceDelete();
 ```
