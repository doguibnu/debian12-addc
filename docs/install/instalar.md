##Baixar o Debian 12

Pode baixar o Debian 12 através [deste](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/) Link ou [deste](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.1.0-amd64-netinst.iso)

**Ao iniciar a instalação:** 

Escolher a linguagem: `Português do Brasil`

Selecionar a localidade: `Brasil`

Configuração do teclado:  `português brasileiro`

Caso sua rede esteja em **DHCP**, eu seleciono voltar no menu de instalação e seleciono a opção **manual** para setar **IP Estático**

**Configurar a rede Manualmente**

Endereço IP:  `seu ip (10.1.1.21 por exemplo)`

máscara de rede: `255.255.255.0`

Gateway: `10.1.1.1 ou seu gateway de saída pra internet`

Servidor de nomes DNS: `selecione um de seu gosto ou da sua rede`

Nome da máquina: `debian12-ad`

Nome do domínio: `seu.dominio`

senha de root: `escolha uma senha de root  `

repita a senha de root: 

Nome completo para o novo usuário: `debian12-ad`

Nome do usuário para sua conta: `debian12-ad`

Informe a senha do usuário: `escolha uma senha de usuário`

repita a senha:

Escolha um fuso horário: `São Paulo`

Metodo de particionamento: `Assistido - usar o disco inteiro ou escolha como desejar`

**Selecione o disco (partição):**

Esquema de Particionamento: `Todos os arquivos em uma partição ou da forma que desejar`

Verifique as configurações do Particionador e selecione `Finalizar o particionamento e escrever as mudanças no disco`

Em Particionar discos analise as mudanças escolha `sim`

**O processo de instalação irá iniciar**

Configurar o gerenciador de pacotes e ler mídia de instalação adicional:`selecionar não`

Configurar o país do gerenciador de pacotes `(repositório: Brasil)` 

Espelho de repositório Debian: `deb.debian.org`

Se não utilizar proxy http, selecione a opção: `continuar`

Configurando popularity-contest: `selecionar não`

Seleção de Softwares: `Selecionar o que desejar + servidor ssh `

Configurar o Grub e instalar o carregador de inicialização no seu disco primário: `selecionar sim`

Informe o particoionamento **(/dev/sda)**, sendo o seu primário

Finalizar a instalação:  `Continuar` 

O sistema irá **Reiniciar**
