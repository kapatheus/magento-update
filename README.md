## Upgrade Magento version 2.3.4 to 2.3.5 follow below steps

```bash
php bin/magento maintenance:enable
composer require magento/product-community-edition 2.3.5 --no-update
composer update
rm -rf var/* pub/static/* generated/*
php bin/magento setup:upgrade
php bin/magento setup:static-content:deploy -f
php bin/magento setup:di:compile
php bin/magento indexer:reindex
php bin/magento cache:clean
php bin/magento cache:flush
```

## After upgrade, check your Magento version with the following command:
```bash
php bin/magento --version
php bin/magento maintenance:disable
```

## Done
