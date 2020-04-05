Automatizar a execução do script:

1° - Baixe o arquivo dentro da pasta /root:

cd /root && wget https://github.com/theuscarvalho/atualizacoordenadasmk-auth/archive/master.zip

2° - Descompacte o arquivo dentro da /root

unzip /root/master.zip

3° - Copie o arquivo para dentro da pasta /opt/mk-auth/scripts

cp /root/atualizacoordenadasmk-auth-master/atualiza_coordenadas.php /opt/mk-auth/scripts/atualiza_coordenadas.php
 
// Crie o token na plataforma do google: https://developers.google.com/maps/documentation/geocoding/get-api-key?hl=pt-br
4° - Altere o token na primeira linha.

nano /opt/mk-auth/scripts/atualiza_coordenadas.php


5° - Permissões de execução

chmod 777 -R /opt/mk-auth/scripts/atualiza_coordenadas.php

6 - Cria rotina no cron. (Pecorre todas as tabelas a procura de novos cadastros)

echo "*/1 * * * * root php /opt/mk-auth/scripts/atualiza_coordenadas.php" >> /etc/crontab

7 - E para finalizar, reboot no cron para iniciar a operação do script.

/etc/init.d/cron restart

Boa sorte!!

Qualquer duvida estou a disposição.

Whatsapp: (79)99998-9976
