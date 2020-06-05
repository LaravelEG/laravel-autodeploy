# LaravelEG Laravel AutoDeploy
Deploy project after pushed commits.
> Support `gitlab` for now.

### Install via composer
```
$ composer require laraveleg/laravel-autodeploy
```

### Publish vendor
- Run `php artisan vendor:publish`
- Selection `LaravelEG\Laravel\AutoDeploy\ServiceProvider`

### Config file
Go to `config/laraveleg/autodeploy.php`
- You can specify the name of the branch you want to pull from:- `'branch_remote' => 'master'`
- You can specify some tasks to run after pull:- 
```php
'tasks' => [
     //
]
```

## Add webhook
You can add webhook to route file `like routes/web.php`
```php
Route::prefix("laraveleg")->group(function () {
    LaravelEG\Laravel\AutoDeploy\WebHook::init();
});
```

## Integrations with gitlab
Publishing projects from the repositorie on gitlab.

### URL (webhook):-
You can use url `<BASE_URL>/laraveleg/deploy/gitlab`

### Secret Token
Add a value you choose but you must add this value in a .env file
```env
KAP_TOKEN=<SECRET_TOKEN>
```