<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

# 🔐 Laravel Middleware - Complete Developer Guide

Middleware in Laravel provides a powerful mechanism for filtering HTTP requests entering your application. It acts as a pipeline layer where each middleware can inspect, modify, or reject the request or response.

---

## 📘 Table of Contents

- [What is Middleware?](#what-is-middleware)
- [Creating Custom Middleware](#creating-custom-middleware)
- [Registering Middleware](#registering-middleware)
  - [Global Middleware](#global-middleware)
  - [Route Middleware](#route-middleware)
- [Applying Middleware to Routes](#applying-middleware-to-routes)
- [Excluding Middleware](#excluding-middleware)
- [Middleware Groups](#middleware-groups)
- [Middleware Aliases](#middleware-aliases)
- [Sorting Middleware](#sorting-middleware)
- [Middleware Parameters](#middleware-parameters)
- [Terminable Middleware](#terminable-middleware)
- [References](#references)

---

## 📌 What is Middleware?

Middleware provides a convenient mechanism for inspecting and filtering HTTP requests entering your application. You can think of it like "layers" requests pass through before reaching your application logic.

Laravel includes several useful middleware out of the box:
- Authentication
- CSRF Protection
- Request Throttling
- CORS Handling

---

## 🛠️ Creating Custom Middleware

Use Artisan to generate a new middleware class:

```bash
php artisan make:middleware EnsureTokenIsValid




https://github.com/halimasa1997/laravel-basics/blob/middleware/middleware
