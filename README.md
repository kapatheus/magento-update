Upgrade Magento version 2.3.4 to 2.3.5 follow below steps:

Magento 2 Version Upgrade Commands.

1) php bin/magento maintenance:enable

2) composer require magento/product-community-edition 2.3.5 --no-update

3) composer update

4) rm -rf var/* pub/static/* generated/*

5) php bin/magento setup:upgrade

6) php bin/magento setup:static-content:deploy -f

7) php bin/magento setup:di:compile

8) php bin/magento indexer:reindex

9) php bin/magento cache:clean

10) php bin/magento cache:flush

After upgrade, check your Magento version with the following command:

11) php bin/magento --version

12) php bin/magento maintenance:disable

Done.
