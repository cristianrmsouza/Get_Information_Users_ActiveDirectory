Script para trazer todos os usuarios do AD filtrando Nome, SamAccount, UPN e Mail

###

A Busca pode ser feita da seguinte forma:


Get-ADUser -SearchBase "OU=usuarios,DC=meudominiolocal,DC=com,DC=br" -Filter * -Properties * | Select Name, SamAccountName,  UserPrincipalName, mail, Enabled | Format-Table Name, SamAccountName, UserPrincipalName, mail -A #| Out-File c:\meulocaldesejado
###
Onde está sendo dito a OU onde vamos procurar, ou também pode ser feito na raiz do dominio.

Get-ADUser -SearchBase "DC=meudominiolocal,DC=com,DC=br" -Filter * -Properties * | Select Name, SamAccountName,  UserPrincipalName, mail, Enabled | Format-Table Name, SamAccountName, UserPrincipalName, mail -A #| Out-File c:\meulocaldesejado\arquivo.csv


