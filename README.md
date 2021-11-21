Automatizar a execução do script:

1° - Baixe o arquivo dentro da pasta /root:

<pre>cd /root && wget https://github.com/theuscarvalho/atualizacoordenadasmk-auth/archive/master.zip</pre>

2° - Descompacte o arquivo dentro da /root

<pre>unzip /root/master.zip</pre>

3° - Copie o arquivo para dentro da pasta /opt/mk-auth/scripts

<pre>cp /root/atualizacoordenadasmk-auth-master/atualiza_coordenadas.php /opt/mk-auth/scripts/atualiza_coordenadas.php</pre>
 
// Crie o token na plataforma do google: https://developers.google.com/maps/documentation/geocoding/get-api-key?hl=pt-br
4° - Altere o token na primeira linha.

<pre>nano /opt/mk-auth/scripts/atualiza_coordenadas.php</pre>


5° - Permissões de execução

<pre>chmod 777 -R /opt/mk-auth/scripts/atualiza_coordenadas.php</pre>

6 - Cria rotina no cron. (Pecorre todas as tabelas a procura de novos cadastros)

<pre>echo "*/1 * * * * root php /opt/mk-auth/scripts/atualiza_coordenadas.php" >> /etc/crontab</pre>

7 - E para finalizar, reboot no cron para iniciar a operação do script.

<pre>/etc/init.d/cron restart</pre>

Boa sorte!!

Qualquer duvida estou a disposição.

Whatsapp: (79)99998-9976
