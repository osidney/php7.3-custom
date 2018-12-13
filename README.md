# php7.3-custom
Instalação PHP 7.3 Custom

apt update && apt install php7.3-fpm php7.3-xml php7.3-bz2 php7.3-zip php7.3-mysql php7.3-intl php7.3-gd php7.3-curl php7.3-soap php7.3-mbstring php7.3-bcmath -y

<b>Descompactando arquivos</b>

wget https://github.com/sidneydevelop/php7.3-custom/archive/master.zip

unzip master.zip

cd php7.3-custom-master/

<b>Copiando Arquivos</b>

cp php.ini /etc/php/7.3/fpm/

cp www.conf /etc/php/7.3/fpm/pool.d/

cp php73.conf /etc/nginx/common/

Altere o arquivo upstream.conf
nano /etc/nginx/conf.d/upstream.conf

De:
php7.0-fpm
upstream php7 {
    server 127.0.0.1:9070;
}

Para:
php7.0-fpm
upstream php7 {
    server 127.0.0.1:9073;
}

<b>Reiniciando Serviços</b>

service nginx reload

service php7.2-fpm reload
