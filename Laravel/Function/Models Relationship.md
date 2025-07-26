Laravel provides powerful **Eloquent ORM (Object-Relational Mapping)** relationships to manage database associations. Here’s a complete guide to Laravel **model relationships** with their **parameters** and options.

---

## **1. One-to-One (`hasOne` and `belongsTo`)**

A **one-to-one** relationship means that one record in a table is associated with one record in another table.

### **Example**

- A **User** has **one** Profile.
- A **Profile** belongs to a **User**.

```php
// User.php Model
class User extends Model
{
    public function profile()
    {
        return $this->hasOne(Profile::class);
    }
}

// Profile.php Model
class Profile extends Model
{
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}
```

### **Optional Parameters**

#### `hasOne(Model::class, 'foreign_key', 'local_key')`

```php
return $this->hasOne(Profile::class, 'user_id', 'id');
```

- **`foreign_key`** → The column on the related table (`profiles.user_id`).
- **`local_key`** → The column on the main table (`users.id`).

#### `belongsTo(Model::class, 'foreign_key', 'owner_key')`

```php
return $this->belongsTo(User::class, 'user_id', 'id');
```

- **`foreign_key`** → The column in the current model (`profiles.user_id`).
- **`owner_key`** → The column in the parent model (`users.id`).

---

## **2. One-to-Many (`hasMany` and `belongsTo`)**

A **one-to-many** relationship means one record is related to multiple records in another table.

### **Example**

- A **User** has **many** Posts.
- A **Post** belongs to a **User**.

```php
// User.php Model
class User extends Model
{
    public function posts()
    {
        return $this->hasMany(Post::class);
    }
}

// Post.php Model
class Post extends Model
{
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}
```

### **Optional Parameters**

#### `hasMany(Model::class, 'foreign_key', 'local_key')`

```php
return $this->hasMany(Post::class, 'user_id', 'id');
```

- **`foreign_key`** → The column in the related table (`posts.user_id`).
- **`local_key`** → The column in the main table (`users.id`).

#### `belongsTo(Model::class, 'foreign_key', 'owner_key')`

```php
return $this->belongsTo(User::class, 'user_id', 'id');
```

- **`foreign_key`** → The column in the current model (`posts.user_id`).
- **`owner_key`** → The column in the parent model (`users.id`).

---

## **3. Many-to-Many (`belongsToMany`)**

A **many-to-many** relationship means multiple records from one table can be related to multiple records in another table using a pivot table.

### **Example**

- A **User** belongs to many **Roles**.
- A **Role** belongs to many **Users**.
- Pivot table: `role_user` (with `user_id` and `role_id`).

```php
// User.php Model
class User extends Model
{
    public function roles()
    {
        return $this->belongsToMany(Role::class);
    }
}

// Role.php Model
class Role extends Model
{
    public function users()
    {
        return $this->belongsToMany(User::class);
    }
}
```

### **Optional Parameters**

#### `belongsToMany(Model::class, 'pivot_table', 'foreign_key', 'related_key', 'parent_key', 'related_parent_key')`

```php
return $this->belongsToMany(Role::class, 'role_user', 'user_id', 'role_id', 'id', 'id');
```

- **`pivot_table`** → The table that connects both models (`role_user`).
- **`foreign_key`** → The column of the current model (`user_id` in `role_user`).
- **`related_key`** → The column of the related model (`role_id` in `role_user`).
- **`parent_key`** → The primary key in the current model (`users.id`).
- **`related_parent_key`** → The primary key in the related model (`roles.id`).

#### **Pivot Table with Additional Fields**

If your pivot table has additional fields like `created_at`, you must enable `withTimestamps()`:

```php
return $this->belongsToMany(Role::class)->withTimestamps();
```

---

## **4. One-to-One (Polymorphic)**

A **one-to-one polymorphic** relationship allows one model to belong to multiple other models.

### **Example**

- A **User** and **Post** both have **one** Image.
- The `images` table has:
    - `imageable_id`
    - `imageable_type` (`User` or `Post`)

```php
// Image.php Model
class Image extends Model
{
    public function imageable()
    {
        return $this->morphTo();
    }
}

// User.php & Post.php Models
class User extends Model
{
    public function image()
    {
        return $this->morphOne(Image::class, 'imageable');
    }
}

class Post extends Model
{
    public function image()
    {
        return $this->morphOne(Image::class, 'imageable');
    }
}
```

### **Optional Parameters**

#### `morphOne(Model::class, 'morph_name', 'type_column', 'id_column', 'local_key')`

```php
return $this->morphOne(Image::class, 'imageable', 'imageable_type', 'imageable_id', 'id');
```

- **`morph_name`** → The prefix (`imageable`).
- **`type_column`** → Stores model type (`imageable_type`).
- **`id_column`** → Stores model ID (`imageable_id`).
- **`local_key`** → The primary key of the parent model.

#### `morphTo()`

No parameters needed.

---

## **5. One-to-Many (Polymorphic)**

A **one-to-many polymorphic** relationship means multiple models can have many records in another table.

### **Example**

- A **User** and **Post** both have many Comments.
- The `comments` table has:
    - `commentable_id`
    - `commentable_type` (`User` or `Post`)

```php
// Comment.php Model
class Comment extends Model
{
    public function commentable()
    {
        return $this->morphTo();
    }
}

// User.php & Post.php Models
class User extends Model
{
    public function comments()
    {
        return $this->morphMany(Comment::class, 'commentable');
    }
}

class Post extends Model
{
    public function comments()
    {
        return $this->morphMany(Comment::class, 'commentable');
    }
}
```

---

## **6. Many-to-Many (Polymorphic)**

A **many-to-many polymorphic** relationship allows multiple models to share many records.

### **Example**

- A **Post** and **Video** both have many Tags.
- The `taggables` pivot table:
    - `tag_id`
    - `taggable_id`
    - `taggable_type`

```php
// Tag.php Model
class Tag extends Model
{
    public function taggables()
    {
        return $this->morphedByMany([Post::class, Video::class], 'taggable');
    }
}

// Post.php & Video.php Models
class Post extends Model
{
    public function tags()
    {
        return $this->morphToMany(Tag::class, 'taggable');
    }
}

class Video extends Model
{
    public function tags()
    {
        return $this->morphToMany(Tag::class, 'taggable');
    }
}
```

---

## **Conclusion**

Laravel provides powerful **relationships** to manage your data efficiently:

- **One-to-One** (`hasOne`, `belongsTo`)
- **One-to-Many** (`hasMany`, `belongsTo`)
- **Many-to-Many** (`belongsToMany`)
- **Polymorphic Relationships** (`morphOne`, `morphMany`, `morphToMany`)

Want help with a specific case? 😊