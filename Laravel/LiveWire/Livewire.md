To use Laravel's standard “stuff” with Vite, we can just go ahead and install our dependencies and run `npm run dev`.

```bash
npm install

# Start Vite's dev server, which
# will watch for file changes
npm run dev 

# Alternatively, build for production 
npm run build
```

```php
php artisan vendor:publish --force --tag=livewire:assets
```