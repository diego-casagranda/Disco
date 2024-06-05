# Disco

ShellScript para pegar informações de uso de disco

```
#!/bin/bash
#
#===============================================================================
#
# File...........: disco.sh
# Title..........: Disco
# Program........: Shell Code -  GNU/Linux
#
# Description....: Exibe informações do disco
#
# Copyright......: Copyright(c) 2024 / @Diego.Casagranda - HackLab
# License........: GNU GENERAL PUBLIC LICENSE - Version 3, 29 June 2007
#
# Author.........: Diego Casagranda
# E-Mail.........: diego.casagranda@mail.ru
#
# Dependency.....: None
#
# Date...........: 05/06/2024
# Update.........: None
#
# Version........: 0.1.0
#
#===============================================================================
#
# ###########
# # History #
# ###########
#
#     05/06/2024 : Criação do codigo
#
#===============================================================================

# pega o disco atual
DISCO_ATUAL=`df -h . | tail -n1 | awk '{print $1}'`

# Pega o tamanho total do disco
TAMANHO=`df -h | grep $DISCO_ATUAL | awk '{print $2}'`

# Pega quanto foi usado já do disco
USADO=`df -h | grep $DISCO_ATUAL | awk '{print $3}'`

# Pega o espaço livre
LIVRE=`df -h | grep $DISCO_ATUAL | awk '{print $4}'`

# Pega a porcentagem de uso do disco
PORCENTAGEM=`df -h | grep $DISCO_ATUAL | awk '{print $5}'`

# Exibe na tela as informações
echo "HD atual de: $TAMANHO, utilizado: $USADO, Espaço Livre: $LIVRE"
```

Você pode movelo para /usr/bin e disponibilizar o comando para todos os usuarios
```
# copiar para /usr/bin
sudo cp disco.sh /usr/bin/

# Permição para usuarios e grupos
sudo chmod 777 /usr/bin/disco.sh

# Tornalo executavel
sudo chmod +x /usr/bin/disco.sh
```
