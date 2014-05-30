`phpers Trójmiasto` – 31.05.2014
================================

Użyłem microframeworka `silex`, żeby w skrócie zaprezentować różne narzędzia raportowania jakości kodu.

Prezentacja znajduje się w pliku `prezentacja.pdf`.

`halleck.html` zawiera raport wygenerowany przez [Halleck's PhpMetrics](https://halleck45.github.io/PhpMetrics/).
Gorąco polecam przeanalizowanie swojego kodu tym narzędziem.

Szybkie sprawdzenie różnych danych „technicznych” projektu: `phpcs src`.

Plik `build.xml` został pobrany z [http://jenkins-php.org/](http://jenkins-php.org/)
i lekko zmodyfikowany na potrzeby prezentacji.
Dorzuciłem także kilka zadań „composerowych”, przydatnych w częstym korzystaniu z tego zajęcia.

`phpcs.xml` opiera się o standard `psr-2`, ale go rozbudowałem o szereg przydatnych do sprawdzania reguł.

Katalog `build` specjalnie załączyłem do commita, żeby móc zobaczyć wygenerowane dane na podstawie projektu.
Polecam zwłaszcza podkatalog `coverage` z pokryciem kodu w testach PHPUnita.

Kilka plików Silex'a zostało specjalnie zmodyfikowanych na potrzeby prezentacji.



W razie pytań, śmiało piszcie na `kontakt@dnowak.pl`.

Dawid Nowak






======




Silex, a simple Web Framework
=============================

Silex is a PHP micro-framework to develop websites based on `Symfony2
components`_:

.. code-block:: php

    <?php

    require_once __DIR__.'/../vendor/autoload.php';

    $app = new Silex\Application();

    $app->get('/hello/{name}', function ($name) use ($app) {
      return 'Hello '.$app->escape($name);
    });

    $app->run();

Silex works with PHP 5.3.3 or later.

Installation
------------

The recommended way to install Silex is through `Composer`_. Just create a
``composer.json`` file and run the ``php composer.phar install`` command to
install it:

.. code-block:: json

    {
        "require": {
            "silex/silex": "~1.1"
        }
    }

Alternatively, you can download the `silex.zip`_ file and extract it.

More Information
----------------

Read the `documentation`_ for more information.

Tests
-----

To run the test suite, you need `Composer`_:

.. code-block:: bash

    $ php composer.phar install --dev
    $ vendor/bin/phpunit

Community
---------

Check out #silex-php on irc.freenode.net.

License
-------

Silex is licensed under the MIT license.

.. _Symfony2 components: http://symfony.com
.. _Composer:            http://getcomposer.org
.. _silex.zip:           http://silex.sensiolabs.org/download
.. _documentation:       http://silex.sensiolabs.org/documentation
