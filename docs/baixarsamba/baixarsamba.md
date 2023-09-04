##Baixar o Samba



**Obs:**  a versão a ser baixada será a `4.18.6`.

Fazer um `diretório` temporário para baixar o samba:

```
mkdir tempsamba
```

Mudar para o diretório criado:

```
cd tempsamba
```

`Baixar` o samba com o comando:

```
wget https://download.samba.org/pub/samba/stable/samba-4.18.6.tar.gz
```

`Descompactar`o arquivo baixado:

```
tar -zxvf samba-nome-arquivo
```

`Mudar` para o diretório onde foi descompactado:

```
cd samba-nome-arquivo/
```

**Compilar** o `samba` para o arquivo de configuração ficar em: `/etc/samba/smb.conf`com o comando:

```
./configure --sysconfdir=/etc/samba/
```

Se não houver nenhum erro, o sistema deve apresentar um resultado parecido como abaixo: 

```
Checking if compiler accepts -fstack-clash-protection : yes 
'configure' finished successfully (1m10.556s)
```

Fazer os comandos `make` e `make install`:

**OBS:** dependendo de sua configuração este procedimento é demorado, então aguarde a finalização:

```
make && make install
```

Se nenhum erro ocorrer no procedimento, o sistema vai mostrar um resultado parecido como abaixo: 

```
Waf: Leaving directory `/root/tempsamba/samba-4.18.6/bin/default'
'install' finished successfully (4m36.452s)
```
