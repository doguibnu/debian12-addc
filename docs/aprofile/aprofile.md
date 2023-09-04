##Editar o arquivo `.profile `



O objetivo é chamar o comando `samba-tool` independente do caminho que você estiver no sistema.

Para editar o arquivo `/root/.profile` faça o comando:

```
nano /root/.profile
```

 Adicionar a linha ao final do arquivo

```
PATH=/usr/local/samba/bin/:/usr/local/samba/sbin/:$PATH
export PATH
```

salvar o arquivo:

Para salvar: `control+o` e para sair: `control+x`

Executar um `reboot:`

```
reboot
```
