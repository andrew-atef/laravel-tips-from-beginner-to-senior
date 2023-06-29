## Table of Contents

1. [Beginner Tips](#beginner-tips)
2. [Intermediate Tips](#intermediate-tips)
3. [Senior Tips](#senior-tips)

## Beginner Tips 

1. **CSRF Field** 
- use @csrf to pass through the CSRF protection middleware.
```php
<form method="POST" action="/route">
    @csrf
    ...
</form>
 ```

## Intermediate Tips 

1. **Stacks** 
- The @stack directive allows you to define a named stack where you can push content from multiple views. 
```php
@stack('scripts')
 ```

- 1) The @push directive is used to add content to a named stack. It is often used within a @push and @endpush block : 
```php
@push('scripts')
    <script src="example.js"></script>
@endpush
 ```
- 2) The @prepend directive is similar to @push, but it adds the content to the beginning of the named stack:
```php
@prepend('styles')
    <link href="example.css" rel="stylesheet">
@endprepend
 ```
- 3) The @prependOnce directive is similar to @prepend, but it only adds the content once. If the content has already been added to the stack, it won't be added again :
```php
@prependOnce('styles')
    <link href="example.css" rel="stylesheet">
@endprependOnce
 ```

- 4) The @once directive is used to render content only once. It ensures that the content is displayed the first time it is encountered and then not repeated:
```php
@once
    <div>This will only be displayed once.</div>
@endonce
 ```
