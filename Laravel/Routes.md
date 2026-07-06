
````markdown
# Laravel Route Methods Cheat Sheet

Laravel හි routes සැකසීමට භාවිතා කළ හැකි method සියල්ල පහත දැක්වේ. මේවා `web.php`, `api.php` වැනි route files තුළ භාවිතා වේ.

---

## 📌 1. Basic Routes

```php
Route::get('/path', [Controller::class, 'method']);
Route::post('/path', [Controller::class, 'method']);
Route::put('/path', [Controller::class, 'method']);
Route::patch('/path', [Controller::class, 'method']);
Route::delete('/path', [Controller::class, 'method']);
Route::options('/path', [Controller::class, 'method']);
````

---

## 📌 2. Route with Closures

```php
Route::get('/hello', function () {
    return 'Hello World';
});
```

---

## 📌 3. Route Parameters

```php
Route::get('/user/{id}', function ($id) {
    return "User ID: " . $id;
});

// Optional parameter
Route::get('/user/{name?}', function ($name = 'Guest') {
    return $name;
});
```

---

## 📌 4. Named Routes

```php
Route::get('/profile', [UserController::class, 'show'])->name('profile');
```

---

## 📌 5. Route Groups

### With Middleware

```php
Route::middleware(['auth'])->group(function () {
    Route::get('/dashboard', function () {
        // Only authenticated users
    });
});
```

### With Prefix

```php
Route::prefix('admin')->group(function () {
    Route::get('/users', [AdminController::class, 'index']);
});
```

### With Namespace

```php
Route::namespace('Admin')->group(function () {
    Route::get('/dashboard', [DashboardController::class, 'index']);
});
```

### With Name Prefix

```php
Route::name('admin.')->group(function () {
    Route::get('/dashboard', [AdminController::class, 'dashboard'])->name('dashboard');
});
```

---

## 📌 6. Route Resource

```php
Route::resource('posts', PostController::class);
```

➡️ මෙය පහත routes automagically සාදයි:

- GET /posts → index
    
- GET /posts/create → create
    
- POST /posts → store
    
- GET /posts/{id} → show
    
- GET /posts/{id}/edit → edit
    
- PUT/PATCH /posts/{id} → update
    
- DELETE /posts/{id} → destroy
    

---

## 📌 7. Route API Resource

```php
Route::apiResource('posts', PostController::class);
```

➡️ `create` සහ `edit` methods නොමැත.

---

## 📌 8. Route Match (Multiple Methods)

```php
Route::match(['get', 'post'], '/contact', [ContactController::class, 'handle']);
```

---

## 📌 9. Route Any (All Methods)

```php
Route::any('/submit', [FormController::class, 'submit']);
```

---

## 📌 10. Redirect Routes

```php
Route::redirect('/old-path', '/new-path');
```

➡️ Default status code: 302  
➡️ Optional: `Route::redirect('/old', '/new', 301);`

---

## 📌 11. View Routes

```php
Route::view('/welcome', 'welcome');

// With data
Route::view('/greeting', 'greeting', ['name' => 'Akila']);
```

---

## 📌 12. Fallback Route

```php
Route::fallback(function () {
    return response()->view('errors.404', [], 404);
});
```

---

## 📌 13. Route Constraints

```php
Route::get('/user/{id}', function ($id) {
    return $id;
})->where('id', '[0-9]+');
```

Multiple constraints:

```php
Route::get('/post/{slug}/{id}', function ($slug, $id) {
    return $slug . ' - ' . $id;
})->where([
    'slug' => '[A-Za-z\-]+',
    'id' => '[0-9]+',
]);
```

---

## 📌 14. Controller Routes (Single Action Controllers)

```php
Route::get('/contact', ContactController::class);
```

➡️ Controller class එක `__invoke` method එකක් තිබිය යුතුය.

---

## 📌 15. Route Macros (Advanced)

```php
Route::macro('adminRoutes', function () {
    Route::get('/admin/dashboard', [AdminController::class, 'dashboard']);
    Route::get('/admin/settings', [AdminController::class, 'settings']);
});
```

Usage:

```php
Route::adminRoutes();
```
