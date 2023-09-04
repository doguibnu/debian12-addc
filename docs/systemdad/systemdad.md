##Serviço systemd para o AD-DC

É um serviço automático para o samba-ad-dc subir com o boot do sistema assim como, parar, reiniciar, habilitar ou desabilitar o samba-ad-dc.

Criar o arquivo em: `/etc/systemd/system/samba-ad-dc.service`com o comando:

```
nano /etc/systemd/system/samba-ad-dc.service
```

`Copie` e`cole` o conteúdo abaixo no seu arquivo:

```
[Unit]
Description=Samba Active Directory Domain Controller
After=network.target remote-fs.target nss-lookup.target

[Service]
Type=forking
ExecStart=/usr/local/samba/sbin/samba -D
PIDFile=/usr/local/samba/var/run/samba.pid
ExecReload=/bin/kill -HUP $MAINPID

[Install]
WantedBy=multi-user.target
```

`salvar` o arquivo

Para salvar: `control+o` e para sair: `control+x`

Executar o`reload` do systemd:

```
systemctl daemon-reload
```

`Habilitar` o samba-ad-dc no boot do sistema:

```
systemctl enable samba-ad-dc
```

`Restart` o serviço do samba-ad-dc:

```
systemctl restart samba-ad-dc
```



Verificar o `status` do samba, usar o comando:

```
systemctl status samba-ad-dc
```

Verificar a versão do samba:

```
smbclient --version
```
