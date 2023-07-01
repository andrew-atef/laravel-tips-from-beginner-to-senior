## Table of Contents

1. [Beginner Tips](#beginner-tips)
2. [Intermediate Tips](#intermediate-tips)
3. [Senior Tips](#senior-tips)

## Beginner Tips 

1. **CSRF Field** 
- use @csrf to pass through the CSRF protection middleware.
```blade
<form method="POST" action="/route">
    @csrf
    ...
</form>
 ```

## Intermediate Tips 

1. **Stacks** 
- The @stack directive allows you to define a named stack where you can push content from multiple views. 
```blade
@stack('scripts')
 ```

- 1) The @push directive is used to add content to a named stack. It is often used within a @push and @endpush block : 
```blade
@push('scripts')
    <script src="example.js"></script>
@endpush
 ```
- 2) The @prepend directive is similar to @push, but it adds the content to the beginning of the named stack:
```blade
@prepend('styles')
    <link href="example.css" rel="stylesheet">
@endprepend
 ```
- 3) The @prependOnce directive is similar to @prepend, but it only adds the content once. If the content has already been added to the stack, it won't be added again :
```blade
@prependOnce('styles')
    <link href="example.css" rel="stylesheet">
@endprependOnce
 ```

- 4) The @once directive is used to render content only once. It ensures that the content is displayed the first time it is encountered and then not repeated:
```blade
@once
    <div>This will only be displayed once.</div>
@endonce
 ```

## Senior Tips 

1. **@include Error Handling** 
- 1) The @includeIf is used if you would like to include a view that may or may not be present : 
```blade
@includeIf('layouts.header')
 ```

- 2) The @includeWhen is used if the given condition is true : 
```blade
@includeWhen(Auth::check(), 'layouts.header')
 ```

- 3) The @includeUnless is used unless a specific condition is true : 
```blade
@includeUnless($isAdmin, 'layouts.header')
 ```

- 4) The @includeFirst is used to includes the first view that exists from the list of views provided : 
```blade
@includeFirst(['layouts.featured', 'layouts.header'])
 ```

