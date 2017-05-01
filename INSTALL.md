```
 2979  2017-05-01 07:37:51 git clone --branch 7.x-1.x https://github.com/NuCivic/dkan.git
 2991  2017-05-01 07:41:38 git tag -l
 2992  2017-05-01 07:42:18 git checkout tags/7.x-1.13.3
 2995  2017-05-01 07:43:18 composer require drush/drush
 2996  2017-05-01 07:43:48 drush make --prepare-install drupal-org-core.make webroot --yes
 2997  2017-05-01 07:51:25 rsync -av . webroot/profiles/dkan --exclude webroot
 2998  2017-05-01 07:51:48 drush -y make --no-core --contrib-destination=./ drupal-org.make webroot/profiles/dkan --no-recursion
 2999  2017-05-01 07:58:08 cd webroot/
 3008  2017-05-01 08:25:54 drush site-install dkan --notify --db-url="pgsql://dkan:odpvta2017@localhost/dkan_odp" | tee dkan_pgsql.log
 3012  2017-05-01 08:51:34 sudo service apache2 restart
 3013  2017-05-01 08:51:42 sudo service php5.6-fpm restart
 3017  2017-05-01 08:53:29 ps ax | grep -Ei "(php|apache|http|sql|java|python|bash)"
 3025  2017-05-01 09:01:57 sudo chown `whoami`.www-data webroot -R
 3026  2017-05-01 09:02:12 cd webroot/
 3027  2017-05-01 09:02:20 drush en radix
 3028  2017-05-01 09:03:09 drush radix "VTA Open Data" --kit=https://github.com/NuCivic/radix-kit-nuboot/archive/master.zip
 3029  2017-05-01 09:04:20 cp ../themes/nuboot_radix/assets/. sites/all/themes/vta_open_data/assets/ -vR
 3030  2017-05-01 09:05:28 mv sites/all/themes/vta_open_data/assets/js/nuboot_radix.script.js sites/all/themes/vta_open_data/assets/js/vta_open_data.script.js
 3032  2017-05-01 09:17:34 cp ~/SCVTA/dkan_mysql/webroot/sites/all/themes/vta_open_data/screenshot.png sites/all/themes/vta_open_data/ -v
 3033  2017-05-01 09:28:38 drush user-create VTA --mail="opendata@vta.org" --password="scvta"; drush user-add-role "administrator" VTA
```