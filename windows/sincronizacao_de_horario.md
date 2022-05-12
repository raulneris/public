# Comandos Uteis para Sincronização de horário no Windows

Esses comando foram utilizados em um controlador de domínio Windows Server 2016. Para a execução dos comandos, é necessário ter privilégios de administrador.

**O Comando abaixo verifica de qual servidor, uma workstation ou server está sincronizando o horário:**

```
w32tm /query /source
```

**Comando para verificar a última sincronização e demais informações de sincronização:**

```
w32tm /query /status
```

**Comando para alterar o servidor NTP, de uma workstation ou server remotamente:**

```
net time \\server /set /yes
```
É necessário alterar "\\\server" para o nome da workstation ou server a ser configurado.

**Os comandos abaixo é para apontar um servidor NTP externo:**

```
net stop w32time
w32tm /config /manualpeerlist:pool.ntp.br,0x8, /syncfromflags:manual
net start w32time
```

**Comando para forçar um refresh/sincronização:**

```
w32tm /resync /rediscover
```
ou
```
w32tm /resync
```

**Comando para verificar o horário dos DCs de todo o domínio:**

```
w32tm /monitor /domain:seudominio
```
É necessário alterar "seudominio" para o nome do domínio que se queira verificar.

**Comando para verificar o fuso (time zone):**

```
w32tm /TZ
```

Referência: https://social.technet.microsoft.com/wiki/pt-br/contents/articles/35460.comandos-uteis-para-sincronizacao-de-horario-no-windows-server-2012-r2-e-outras-versoes-do-windows.aspx
