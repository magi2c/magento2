# Installation

```bash
sh m2devbox-init.sh

# Optional. You can add an alias to your .bashrc
echo "alias magento='docker-compose exec --user magento2 web bin/magento'"

# After restart your terminal, you can run `magento` and show the result.
```

## Composer Setup

### Authentication

Please first setup Magento Marketplace authentication (details at <a href="http://devdocs.magento.com/guides/v2.0/install-gde/prereq/connect-auth.html" target="_blank">http://devdocs.magento.com/guides/v2.0/install-gde/prereq/connect-auth.html</a>).

Place your auth token at `~/.composer/auth.json` with the following contents, like so:

```
{
    "http-basic": {
        "repo.magento.com": {
            "username": "MAGENTO_PUBLIC_KEY",
            "password": "MAGENTO_PRIVATE_KEY"
        }
    }
}
```

Then, just set `M2SETUP_USE_ARCHIVE` to `false` in your docker-compose.yml file. 

## Sample Data

If you want install the __sample data__:

```bash
magento sampledata:deploy
```


### Notes:

```bash
# Entering to container:
docker-compose exec --user magento2 web bash

# 
docker-compose exec --user magento2 web composer install

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

