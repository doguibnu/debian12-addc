##Provisionar o Samba (modo interativo):

Verifique o ip com o comando:

```
ip a
```

O resultador pode parecer com este abaixo:

2: **ens18:** <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 8e:a2:1e:57:9a:9e brd ff:ff:ff:ff:ff:ff
    altname enp0s18
    inet 10.1.1.21/8 brd 10.255.255.255 scope global ens18

Então, seu dispositivo de rede é o **ens18**

Remover  o arquivo `smb.conf` com o comando:

```
rm /etc/samba/smb.conf
```

**Provisionar o Samba**

Utilizar o comando abaixo:

```
samba-tool domain provision --use-rfc2307 --interactive --option="interfaces= lo ens18" --option="bind interfaces only=yes"
```

Responda as questões referente **sua configuração**

Realm: `SEU.Dominio`

Domain [AD]: `Domínio`

Server Role (dc, member, standalone) [dc]: `dc`

DNS backend (SAMBA_INTERNAL, BIND9_FLATFILE, BIND9_DLZ, NONE) SAMBA_INTERNAL]: `SAMBA_INTERNAL `

DNS forwarder IP address (write 'none' to disable forwarding) [SEU_IP_DNS]:`IP DNS`

Administrator password: `selecionar uma senha`

Retype password: `repetir a senha anterior`

**GUARDE SUA SENHA**

Configure o `kerberos`utilizando o comando:

```
cp /usr/local/samba/private/krb5.conf /etc/krb5.conf
```

**Iniciar o Samba**

Utilizar o comando:

```
samba
```

**Criando zona reversa**


Criar uma zona reversa. **Substitua com o seu IP**. Use o comando:

```
samba-tool dns zonecreate 10.1.1.21 0.99.10.in-addr.arpa -U Administrator
```

`Password for [domains\Administrator]: UTILIZAR A SENHA DE PROVISIONAMENTO
Zone 0.99.10.in-addr.arpa created successfully`

**Verificar o file server:**
Faça o comando:

```
smbclient -L localhost -N
```

Anonymous login successful

    Sharename       Type      Comment
    ---------       ----      -------
    sysvol          Disk      
    netlogon        Disk      
    IPC$            IPC       IPC Service (Samba 4.18.6)
    SMB1 disabled -- no workgroup available

**Verificando a autenticação com o netlogon**

Utilizar o comando abaixo:

```
smbclient //localhost/netlogon -UAdministrator -c 'ls'
```

O comando vai pedir a senha de provisionamento do samba

```
Password for [SEU\Administrator]:
 . D 0 Thu Aug 31 14:43:08 2023
 .. D 0 Thu Aug 31 14:43:17 2023
```

    31861548 blocks of size 1024. 26686664 blocks availableIniciar o samba 

```

```
