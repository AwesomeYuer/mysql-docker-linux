We can avoid this error by make it work with old password plugin:

First change the authentication plugin in my.cnf file for Linux / my.ini file in Windows:

[mysqld]

default_authentication_plugin=mysql_native_password


sudo docker run \
    --hostname microshaoft-gitlab.eastus.cloudapp.azure.com \
    --env GITLAB_OMNIBUS_CONFIG="external_url 'http://my.domain.com/'; gitlab_rails['lfs_enabled'] = true;" \
    --publish 443:443 --publish 80:80 --publish 2222:22 \
    --name gitlab \
    --restart always \
    --volume /mnt/sda1/gitlab/config:/etc/gitlab \
    --volume /mnt/sda1/gitlab/logs:/var/log/gitlab \
    --volume /mnt/sda1/gitlab/data:/var/opt/gitlab \
    gitlab/gitlab-ce:latest



    docker run --name microshaoft-mysql -p 3306:3306 -v /var/lib/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=withoutpassword mysql:latest



    docker run --name microshaoft-mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=withoutpassword mysql:microshaoft

    alter user root@localhost identified with mysql_native_password by 'passwordwithout'


    set global default_authentication_plugin='mysql_native_password'