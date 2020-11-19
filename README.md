# ProFTP
Config File - ProFTP

Fedora, OpenSUSE, CentOS/RHEL 7
# yum install -y proftpd openssl proftpd-utils

Iniciando o serviço e habilitando a inicialização automática

# systemctl start proftpd.service
# systemctl enable proftpd.service

Arquivo de configuração
# vim /etc/proftpd.conf


Habilitando o serviço no Firewall

# firewall-cmd --add-service=ftp --permanent
# firewall-cmd --reload

Criando o Grupo FTP e Adicionando um Usuário
 Edite o arquivo /etc/shells e adicione a linha /bin/false

# vim /etc/shells

Crie um grupo chamado "ftpgroup" e após crie um usuário e o adicione a este grupo.

# groupadd ftpgroup

Agora vamos criar um usuário no grupo groupftp e apontar sua home para a pasta do apache, fazendo assim com que ele se conecte apenas com a pasta /var/www/


# useradd USUARIODOFTP -s /bin/false -d /var/www/ -G ftpgroup
# passwd USUARIODOFTP
