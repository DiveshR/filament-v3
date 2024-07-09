<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

## About Filament Version 3

A collection of beautiful full-stack components.
The perfect starting point for your next app.

 - https://filamentphp.com/docs

 ### Requirements

Filament requires the following to run:

PHP 8.1+
Laravel v10.0+
Livewire v3.0+

### Installation

```
composer require filament/filament:"^3.2" -W
 
php artisan filament:install --panels
```


#### Create a user

```
php artisan make:filament-user
```

Open /admin in your web browser, sign in, and start building your app!

- We can change menu icons from heroicons

- https://heroicons.com/

### Relationship

Instead of
->options(Category::all()->pluck('name', 'id')), in Category Resource

We can use 
 ->relationship('category','name')

### To show a lists of posts of in single cateory using  Realationship manager

https://filamentphp.com/docs/3.x/panels/resources/relation-managers

php artisan make:filament-relation-manager CategoryResource posts title

- ```CategoryResource``` is the name of the resource class for the owner (parent) model.
- ```posts``` is the name of the relationship you want to manage.
- ```title``` is the name of the attribute that will be used to identify posts.

Include relational manger file inside getRelations in resource file which is CategoryResource file in our case.

```
    public static function getRelations(): array
    {
        return [
            PostsRelationManager::class,
        ];
    }
```

