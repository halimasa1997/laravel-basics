<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# 🚦 Laravel Routing Example

Welcome to the **Routing** example branch of this Laravel Basics project!

---

## 📚 What is Routing?

Routing is a fundamental part of Laravel. It allows you to define the URLs (endpoints) your application responds to and what code should execute when those URLs are accessed.

---

## 💻 Example Code

Here’s a simple route defined in `routes/web.php`:

```php
Route::get('/hello', function () {
    return ' Hello My name is Halima and this is Laravel Routing!';
});
