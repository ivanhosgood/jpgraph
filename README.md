## JPGRAPH 3.6.7, Community Edition
## Forked from https://github.com/HuasoFoundries/jpgraph


This is an unnoficial refactor of [JpGraph](http://jpgraph.net/) with the following differences:
- the app was fully refactored adding namespaces, proper folder hierarchy, separating each class in its own file and stripping the use of `require` and `include` to the bare minimum
- dropping support for PHP < 5.4. 
- it provides full composer compatibility
- it has PSR-4 autoloading
- it makes requirement checks so you can't go wrong
- it has release tags, to let `composer install` use your cached packages instead of pulling from github every time
- I stripped the docs because they are useless weight in a dependency. [You can find them here](http://jpgraph.net/doc/)
- The Examples folder were moved upwards, althought they are now in categories. Not all of them work at this point
- Examples pointing to features not present in the free tool were stripped from said folder (e.g. Barcodes)
- If the chosen font isn't found, it falls back to existing fonts instead of crashing
- If you try to use antialiasing functions not present in your current GD installation, it disables them instead of crashing


## How to install

Using composer

```sh
composer require ivanhosgood/jpgraph
```

## How to use

See the [examples folder](https://github.com/ivanhosgood/jpgraph/tree/master/Examples) for working samples. 

The examples work the same way you should use this library:

   - run `composer install`

   - require `vendor/autoload.php` it the top of your script

   - generate a graph with a snippet like the following

   ```php
   use Amenadiel\JpGraph\Graph;
   use Amenadiel\JpGraph\Plot;

   $graph = new Graph\PieGraph(350, 250);
   $graph->title->Set("A Simple Pie Plot");
   $graph->SetBox(true);

   $data = array(40, 21, 17, 14, 23);
   $p1 = new Plot\PiePlot($data);
   $p1->ShowBorder();
   $p1->SetColor('black');
   $p1->SetSliceColors(array('#1E90FF', '#2E8B57', '#ADFF2F', '#DC143C', '#BA55D3'));


   $graph->Add($p1);
   $graph->Stroke();
   ```

See the examples working by performing the following steps:

 - `composer install`
 - `php -S localhost:8000`
 - Open your browser at http://localhost:8000/Examples/index.html






### Wishlist

- Get all the examples working
- If the project gains traction I can move the repo to an organization so there can be more mantainers and contributions
- Add tests
- Add CI tools
- Add alternative use of [imagick](http://php.net/manual/en/imagick.setup.php) 




![jpgraph_logo](https://raw.githubusercontent.com/HuasoFoundries/jpgraph/master/jpgraph_logo.jpg)

README FOR JPGRAPH 3.5.x
=========================

This package contains the JpGraph PHP library Pro version 3.5.x

The library is Copyright (C) 2000-2010 Asial Corporatoin and
released under dual license QPL 1.0 for open source and educational
use and JpGraph Professional License for commercial use. 

Please see full license details at 
http://jpgraph.net/pro/
http://jpgraph.net/download/

* --------------------------------------------------------------------
* PHP4 IS NOT SUPPORTED IN 2.x or 3.x SERIES
* --------------------------------------------------------------------
			
Requirements:
-------------
Miminum:
* PHP 5.1.0 or higher 
* GD 2.0.28 or higher
Note: Earlier versions might work but is unsupported.

Recommended:
* >= PHP 5.2.0
* PHP Builtin GD library

Installation
------------
1. Make sure that the PHP version is compatible with the stated 
   requirements and that the PHP installation has support for 
   the GD library. Please run phpinfo() to check if GD library 
   is supported in the installation. 
   If the GD library doesn't seem to be installed 
   please consult the PHP manual under section "Image" for
   instructions on where to find this library. Please refer to
   the manual section "Verifying your PHP installation"
   
2. Unzip and copy the files to a directory of your choice where Your
   httpd sever can access them. 
   For a global site installation you should copy the files to 
   somewhere in the PHP search path. 

3. Check that the default directory paths in jpg-config.inc.php
   for cache directory and TTF directory suits your installation. 
   Note1: The default directories are different depending on if
   the library is running on Windows or UNIX.
   Note2: Apache/PHP must have write permission to your cache 
   directory if you enable the cache feature. By default the cache
   is disabled.
   

Documentation
-------------
The installation includes HTML documentation and reference guide for the
library. The portal page for all documentation is
<YOUR-INSTALLATION-DIRECTORY>/docs/index.html


Bug reports and suggestions
---------------------------
Should be reported using the contact form at

http://jpgraph.net/contact/

