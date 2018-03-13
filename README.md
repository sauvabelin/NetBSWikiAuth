# NetBSAuth
This wiki extension was first created to allow netBS users to log into the wikiBS.

Passwords must be hashed using the sha512 algorithm and base64 encoded
## Installation
1. Clone this repository into your wiki `/extensions` directory
2. run `composer install` from within the extension directory
2. Configure this extension in your `LocalSettings.php`

```php
require_once './extensions/NetBSAuth/NetBSAuth.php';
$wgAuth    = new NetBSAuth([
    'host'              => 'localhost',
    'database'          => 'symfony',
    'username'          => 'root',
    'password'          => 'root',
    'table'             => 'wiki_users',
    'usernameColumn'    => 'username',
    'hashColumn'        => 'password',
    'saltColumn'        => 'salt',
    'bcrypt_cost'       => 5000
]);
```