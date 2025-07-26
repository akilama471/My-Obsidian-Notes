Here’s a comprehensive list of **Laravel Eloquent Model methods** (including query builder methods used via Eloquent) with **examples** that you can add to your Obsidian documentation.

---

## 📄 Laravel Eloquent Model & Query Methods

### 🔹 `all()`

Returns all records from a model.

```php
$users = User::all();
```

### 🔹 `get()`

Executes the query and returns a collection.

```php
$users = User::where('active', true)->get();
```

### 🔹 `first()`

Returns the first result of the query.

```php
$user = User::where('email', 'john@example.com')->first();
```

### 🔹 `find($id)`

Finds a model by primary key.

```php
$user = User::find(1);
```

### 🔹 `findOrFail($id)`

Find or throw a `ModelNotFoundException`.

```php
$user = User::findOrFail(1);
```

### 🔹 `firstOrFail()`

Same as `first()`, but throws an exception if no result found.

```php
$user = User::where('email', 'john@example.com')->firstOrFail();
```

### 🔹 `firstOrCreate(array $attributes, array $values = [])`

Gets the first record matching attributes or creates it.

```php
$user = User::firstOrCreate(
    ['email' => 'john@example.com'],
    ['name' => 'John Doe']
);
```

### 🔹 `firstOrNew(array $attributes, array $values = [])`

Same as `firstOrCreate` but doesn’t persist to the database.

```php
$user = User::firstOrNew(
    ['email' => 'john@example.com'],
    ['name' => 'John Doe']
);
```

### 🔹 `updateOrCreate(array $attributes, array $values = [])`

Update a record if it exists, otherwise create it.

```php
$user = User::updateOrCreate(
    ['email' => 'john@example.com'],
    ['name' => 'Johnny']
);
```

### 🔹 `pluck('column')`

Retrieves values of a single column.

```php
$emails = User::pluck('email');
```

### 🔹 `count()`

Returns the number of records.

```php
$total = User::count();
```

### 🔹 `exists()`

Returns true if records exist.

```php
$exists = User::where('email', 'john@example.com')->exists();
```

### 🔹 `doesntExist()`

Opposite of `exists()`.

```php
$notExists = User::where('email', 'ghost@example.com')->doesntExist();
```

### 🔹 `orderBy()`

Sorts the results.

```php
$users = User::orderBy('name', 'asc')->get();
```

### 🔹 `latest()` / `oldest()`

Sorts by `created_at` descending / ascending.

```php
$latestUser = User::latest()->first();
```

### 🔹 `limit()` / `take()`

Limits the number of records.

```php
$users = User::limit(5)->get();
```

### 🔹 `skip()` / `offset()`

Skips a number of records.

```php
$users = User::skip(10)->take(5)->get();
```

### 🔹 `where()`

Filters the query.

```php
$users = User::where('status', 'active')->get();
```

### 🔹 `orWhere()`

Adds an OR clause.

```php
$users = User::where('role', 'admin')->orWhere('role', 'editor')->get();
```

### 🔹 `whereIn()`

Checks if a column value is in a list.

```php
$users = User::whereIn('id', [1, 2, 3])->get();
```

### 🔹 `whereBetween()`

Checks if a column value is between two values.

```php
$users = User::whereBetween('age', [18, 30])->get();
```

### 🔹 `with()`

Eager loads relationships.

```php
$users = User::with('posts')->get();
```

### 🔹 `has()` / `whereHas()`

Filters by existence of relationships.

```php
$users = User::has('posts')->get();
$users = User::whereHas('posts', function ($q) {
    $q->where('title', 'like', '%Laravel%');
})->get();
```

### 🔹 `create(array $data)`

Creates and saves a new model instance.

```php
$user = User::create([
    'name' => 'John Doe',
    'email' => 'john@example.com',
    'password' => bcrypt('secret'),
]);
```

### 🔹 `save()`

Saves a model instance.

```php
$user = new User();
$user->name = 'Jane';
$user->save();
```

### 🔹 `update(array $data)`

Updates a model instance.

```php
$user->update(['name' => 'Updated Name']);
```

### 🔹 `delete()`

Deletes a model.

```php
$user->delete();
```

### 🔹 `destroy(id)`

Deletes one or multiple records by ID.

```php
User::destroy([1, 2, 3]);
```

### 🔹 `softDeletes()`

Use `SoftDeletes` trait for soft deleting.

```php
use Illuminate\Database\Eloquent\SoftDeletes;

class User extends Model {
    use SoftDeletes;
}
```

### 🔹 `onlyTrashed()` / `withTrashed()` / `restore()`

Work with soft-deleted models.

```php
User::onlyTrashed()->get();
User::withTrashed()->get();
User::withTrashed()->find(1)->restore();
```

### 🔹 `toArray()` / `toJson()`

Convert models to arrays or JSON.

```php
$userArray = $user->toArray();
$userJson = $user->toJson();
```

---

Would you like this exported to a `.md` file for Obsidian or need it grouped by CRUD, Relationship, Query Scopes, etc.?