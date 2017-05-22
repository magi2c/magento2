```bash
docker-compose up --build -d
```

```bash
docker-compose exec --user magento2 web php /var/www/magento2/bin/magento setup:install \
--db-host=db \
--db-name=magento2 \
--db-user=root \
--db-password=root \
--admin-firstname=Magento \
--admin-lastname=User \
--admin-email=user@example.com \
--admin-user=admin \
--admin-password=admin123 \
--language=en_US \
--currency=USD \
--timezone=America/Chicago \
--use-rewrites=1 \
--backend-frontname=admin
```

```bash
docker-compose exec --user magento2 web bash
```
