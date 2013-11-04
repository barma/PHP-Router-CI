PHP-Router-CI
=============

PHP router from CodeIgniter

If you are not afraid of the Russian language, you can read a small article about it here 
http://zhuykov.ru/blog/show_post.php?id=21

To see how this class can open http://your-test-domain/index.php/product/12/

index.php

<?

$route['product/(:num)'] = "catalog2/start/$1";
$route['default_controller'] = "welcome";
$route['404_override'] = '';
$route['directory'] = 'my_directory';

require_once "Router.php";

$rtr = new Router();
$rtr->_set_routing($route);


// Set any routing overrides that may exist in the main index file
if (isset($routing))
{
$rtr->_set_overrides($routing);
}


echo "<br>DIR = ".$rtr->fetch_directory()."<br>CLASS = ".$rtr->fetch_class();
echo "<br>METHOD = ".$rtr->fetch_method();
