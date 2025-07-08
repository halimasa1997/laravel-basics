<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# 🔐 Laravel Middleware - Complete Developer Guide



# Middleware in Laravel

## Definition
Middleware are HTTP filters that handle requests before they reach the controller or after they are processed. They act as a bridge between a request and a response, allowing you to filter and modify HTTP requests entering your application.

## Creating Middleware

Use the Artisan command to generate a new middleware class:

```bash
php artisan make:middleware CheckAge
```

This command creates a new middleware file in the `app/Http/Middleware` directory.

## Middleware Example

Here's a basic example of a middleware that checks if a user is over 18:

```php
<?php

namespace App\Http\Middleware;

use Closure;

class CheckAge
{
    public function handle($request, Closure $next)
    {
        if ($request->age <= 18) {
            return redirect('home');
        }

        return $next($request);
    }
}
```

The middleware receives the request and a closure (`$next`) that represents the next middleware in the pipeline. If the age condition is not met, it redirects to the home page; otherwise, it passes the request to the next middleware.

## Registering Middleware

To use your middleware, you need to register it in the `app/Http/Kernel.php` file:

```php
// In app/Http/Kernel.php
protected $routeMiddleware = [
    'check.age' => \App\Http\Middleware\CheckAge::class,
];
```

This registers the middleware with a key (`check.age`) that you can use to reference it in routes and controllers.

## Using Middleware

### In Routes

Apply middleware directly to routes:

```php
// In routes file
Route::get('/admin', function () {
    return 'Admin Panel';
})->middleware('check.age');
```

### In Controllers

Apply middleware in controller constructors:

```php
class UserController extends Controller
{
    public function __construct()
    {
        $this->middleware('auth');
        $this->middleware('check.age')->only('show');
    }
}
```

You can use `only()` to apply middleware to specific methods or `except()` to exclude certain methods.

## Global Middleware

Global middleware runs on every HTTP request to your application. Register it in the `$middleware` array:

```php
// In app/Http/Kernel.php
protected $middleware = [
    \App\Http\Middleware\TrustProxies::class,
    \App\Http\Middleware\CheckForMaintenanceMode::class,
];
```

## Middleware Types

- **Global Middleware**: Runs on all requests
- **Route Middleware**: Runs on specific routes or route groups
- **Controller Middleware**: Applied within controller constructors

## Common Use Cases

- Authentication and authorization
- CORS handling
- Request validation
- Rate limiting
- Logging
- Security checks

## Best Practices

1. Keep middleware focused on a single responsibility
2. Use descriptive names for middleware aliases
3. Consider performance impact for global middleware
4. Test middleware thoroughly as they affect all requests
5. Use middleware groups for related functionality


## 🛠️ Creating Custom Middleware

Use Artisan to generate a new middleware class:


php artisan make:middleware EnsureTokenIsValid


https://github.com/halimasa1997/laravel-basics/blob/middleware/middleware
