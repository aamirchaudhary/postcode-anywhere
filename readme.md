# Laravel API wrapper for PCA Predict formerly Postcode Anywhere

This wrapper simplifies process of making API calls to [**PostcodeAnywhere**](http://www.postcodeanywhere.co.uk/)  web services.
Single line of code within your [**Laravel**](http://laravel.com/) application that's all it takes.


Dependency
------------
[**PHP cURL**] (http://php.net/manual/en/curl.installation.php) required


Installation
------------

To install edit `composer.json` and add following line:

```javascript
"alexpechkarev/postcode-anywhere": "dev-master"
```

Run `composer update`


Configuration
-------------

Once installed, register Laravel service provider, in your `config/app.php`:

```php
'providers' => [
	...
    'Alexpechkarev\PostcodeAnywhere\PAServiceProvider',
]

'aliases' => [
	...
    'PA'        => 'Alexpechkarev\PostcodeAnywhere\PAFacade' ,
]
```

Publish configuration file `php artisan vendor:publish` .
To access the services do not forget to update the service key in configuration file. 

Usage
-----

```php
$response = \PA::getRespose(['find' =>'FindByPostcode', 'param'=>['postcode' => 'SW1A 1AA', 'endpoint' => 'json'] ]);

or

$response = \PA::getRespose(['retrive' =>'RetrieveById', 'param'=>['id' => '23747212.00', 'endpoint' => 'json'] ]);
```



Support
-------

[Found errors or to suggest improvements please open an issue on GitHub](https://github.com/alexpechkarev/postcode-anywhere/issues)


License
-------

Laravel API wrapper for PCA Predict formerly Postcode Anywhere is released under the MIT License. See the bundled
[LICENSE](https://github.com/alexpechkarev/postcode-anywhere/blob/master/LICENSE)
file for details.