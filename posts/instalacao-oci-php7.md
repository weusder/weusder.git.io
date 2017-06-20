Intalação da extenção oci e PDO OCI no PHP 

Instalando driver oci para php

Instalar oracle client

 ... passos para instalação do client

Iremos baixar a extenção via php-pear

caso não esteja instalado executar o comando:

dnf install php-pear

para instalar a extenção execute o comando

pecl install oci8

Quando for solicitado a localização do client oracle informe conforme abaixo

instantclient,/usr/lib/oracle/11.2/client64/lib

Nota: 11.2 é a versão do client que esta instalado, poderá variar de acordo com o seu ambiente

Caso queira instalar o client da versão 12, recomendamos que instale o 12.1

Ao concluir a instalação digite o comando abaixo para habilitar a extenção 

echo extension=oci8.so > /etc/php.d/oci.ini

Instalando driver OCI para PDO

Verificar a versão do php que está instalado

php -v

No nosso exemplo está instalado a versão 7.0.20

Baixar o código fonte do php na mesma versão que esta instlado

Descompactar o arquivo, depois acessar 

php-7.0.20/ext/pdo_oci

digiar o comando

phpize

./configure --with-pdo-oci=instantclient,/usr,11.2

Nota: 11.2 é a versão do oracle client que está instalado

make
make install

Digite o comando abaixi para habilitar a extenção no arquivo de configuração

echo extension=pdo_oci.so > /etc/php.d/pdo_oci.ini

Fonte: 
https://github.com/CakeDC/cakephp-oracle-driver/blob/master/docs/Php7PdoOciExtensionSetup.md

https://github.com/NatLibFi/NDL-VuFind2/wiki/Oracle-with-PHP-5.6-or-PHP-7-on-RHEL-6-or-CentOS-7


