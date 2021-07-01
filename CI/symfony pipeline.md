## CI workflow

* code style ([PHP-CS-Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer))
* static analysis ([Psalm](http://psalm.dev/), [PHPStan](https://phpstan.org/), [PHPMD](https://phpmd.org/))
  * [Magic number detector](https://github.com/povils/phpmnd)
    phpmnd src -v --progress --ignore-numbers=2,-1 --extensions=all --non-zero-exit-on-violation
* composer:
  * .json/lock [validate](https://getcomposer.org/doc/03-cli.md#validate)
  * [unused](https://github.com/composer-unused/composer-unused) dependencies
  * avoid soft dependencies [checker](https://github.com/maglnet/ComposerRequireChecker)
  * [Roave Security](https://github.com/Roave/SecurityAdvisories) [Advisories](https://github.com/Roave/SecurityAdvisories), [Local PHP Security Checker](https://github.com/fabpot/local-php-security-checker)
* bin/console lint:yaml config --parse-tags, bin/console lint:yaml src
* bin/console lint:twig
* bin/console lint:container
* bin/console debug:container --deprecations
* doctrine:
  * bin/console doctrine:schema:validate
  * bin/console doctrine:ensure-production-settings --env=prod
* App architecture layer dependencies checks [Deptrac](https://github.com/qossmic/deptrac), [dePHPend](https://github.com/mihaeu/dephpend)
* All types of tests you have