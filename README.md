# Steam OpenID Provider for Laravel Socialite

[![Scrutinizer Code Quality](https://img.shields.io/scrutinizer/g/SocialiteProviders/Steam.svg?style=flat-square)](https://scrutinizer-ci.com/g/SocialiteProviders/Steam/?branch=master)
[![Latest Stable Version](https://img.shields.io/packagist/v/socialiteproviders/steam.svg?style=flat-square)](https://packagist.org/packages/socialiteproviders/steam)
[![Total Downloads](https://img.shields.io/packagist/dt/socialiteproviders/steam.svg?style=flat-square)](https://packagist.org/packages/socialiteproviders/steam)
[![Latest Unstable Version](https://img.shields.io/packagist/vpre/socialiteproviders/steam.svg?style=flat-square)](https://packagist.org/packages/socialiteproviders/steam)
[![License](https://img.shields.io/packagist/l/socialiteproviders/steam.svg?style=flat-square)](https://packagist.org/packages/socialiteproviders/steam)

## Configuration

`Socialite` expects its drivers to conform within the OAuth specifications. Unfortunately, Steam doesn't offer an OAuth solution, but rather OpenID. Because of this, we need to specify only an API key and a redirect URI. However, the `SocialiteProviders/Manager` package requires us to specify all three configuration keys (`client_id`, `client_secret` and `redirect`) and thus we must set the `client_id` to any value, regardless of it not being utilised.

#### config/services.php
```php
'steam' => [
    'client_id' => null,
    'client_secret' => env('STEAM_KEY'),
    'redirect' => env('STEAM_REDIRECT_URI'),
],
```

#### .env
```
// other values above
STEAM_KEY=yourapikeyfortheservice
STEAM_REDIRECT_URI=https://example.com/login   
```

## Documentation

Full documentation for using this provider can be found at [Steam Documentation](http://socialiteproviders.github.io/providers/steam/)
