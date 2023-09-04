##Lincando libnss_winbind.so.2 (para debian)

Quando o samba é instalando por modo de compilação é necessário fazer os comandos para linkar a `libnss_winbind.so.2`

Os comandos são:

```
ln -s /usr/local/samba/lib/libnss_winbind.so.2 /lib/x86_64-linux-gnu/
ln -s /lib/x86_64-linux-gnu/libnss_winbind.so.2 /lib/x86_64-linux-gnu/libnss_winbind.so
ldconfig
```
