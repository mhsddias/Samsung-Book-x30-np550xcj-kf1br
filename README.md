# SAMSUNG BOOK X30 NP550XCJ-KF1BR
### EFI Opencore 0.9.0 MACOS VENTURA

## Instalação Online (Necessário Cabo de Rede ligado a internet)


### Baixando a Imagem do MacOS, para Instalação Online

1.- Tenha o "PYTHON" instalado no seu windows, linux ou mac, para executar o "Macrecovery" e baixar os arquivos de instalação online do MacOS Ventura. Necessário cabo de rede conectado a internet!

  1.1- Execute o comando para baixar
  py macrecovery.py -b Mac-B4831CEBD52A0C4C -m 00000000000000000 -os latest download
  esse poderá variar caso tenha versões mais recentes do MacOS use o arquivo recovery_urls.txt para saber mais.

  1.2- Ao fazer o Download corretamente terá uma pasta com o nome baixar "com.apple.recovery.boot" que deverá ser copiada para a raíz da sua partição como nome EFI, detalhes de como criar essa partição no ponto 2.

  1.3- Copie os arquivo para pasta EFI em sua partção de nome EFI, contendo os arquivos BOOT e OC, ficará dessa forma:
  Partição "EFI" /EFI/BOOT e /EFI/OC


## Particionando o HD, SSD ou NVME

2. Use um linux para particionar corretamente seu HD, SSD ou NVME. (Recomendo Fedora 38) (Usei o "Gnome Disk Utility" para particionar)
  
  2.1- A primeira partição deve conter 2gb formato Exfat, e ativa para bootar ou inicilizar,lembre de desligar o "Security Boot na Bios" para que o boot funcione. Na partição lembre de colocar os arquivos do ponto 1.2. Observação esta deverá ser a primeira partição do Disco ou HD, SSD, NVME.
  
  2.2- Crie também no linux outra partição com espaço necessário para instalação do MacOS Ventura, no formato Exfat também, para que seja reconhecida na instalação do mesmo. Esta não tem ordem poderá ser a segunda ou terceira partição, etc.
  
  2.3- inicilize o boot do Opencore precionando F10 ao iniciar o Notebook, ao inicilizar a instalador do MacOS formate a partição Exfat para o formato APFS exigido pelo MacOs, seguindo o exemplo do ponto 2.2, e instale online o Mac. Com cabo de rede!

  2.4- Uma Dica, poderá criar um pendrive da mesma forma para instalação Online usando o ponto 2. da mesma forma. Mas ainda irá precisar criar a partição EFI e a partição do MacOS, caso já tenha algum sistema instalado com windows ou Linux eles têm uma partição EFI, onde você precisará colocar os arquivos do ponto 1. Mas será melhor fazer do zero!
  Faça backup antes de qualquer formatação!


## Instalando outros sistemas operacionais

3.- Todos os sitemas operacionais devem ser instalados nessa ordem para dar certo, Windows o primeiro, Linux o segundo e o MacOS por último. Mas o particionamento do HD deve ser antes de quaisquer instalação, criando antes de tudo a partição EFI fucionar corretamente com os arquivos de instalção. Veja o ponto 2. para fazer o particionamento correto.
Lembre, faça backup antes de qualquer formatação! poderá também redimencionar uma partição para criar outra, poderá ser para o Mac ou para fazer o Backup!


## Instalação Offline

4.- Baixe  a imagem do "Ventura 13.2.1 with EFI folder for chipset series 300, 400 and 500"  no site Olarila:
Baixe a Imagem completa do MacOS Ventura pelo site: https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/

  4.1- Precisa de um pendrive com 16gb ou mais, teclado e mouse USB externo;
  
  4.2- Use o Balena Etcher para gravar a imagem no pendrive;
  https://www.balena.io/etcher/
  
  4.3- Crie uma partição ou redimensione alguma e crie uma partição exclusiva para o MacOS no formato Exfat onde deseja instalar o mesmo, caso já tenha um sistema instalado, e queira fazer tudo novo e apagar tudo faça o ponto 2. para uma instalação nova.
  
  4.4- Após instalação substitua a EFI do pendrive pela aqui baixada usando o ESP mounter pro, encontrado na imagem baixada no site olarila e gravado no pendrive ou pelo próprio site olarila.
  https://www.olarila.com/files/Utils/ESP%20Mounter%20Pro.app_v1.9.1.zip
  Assim como no ponto 1 copiando para partição EFI a pasta EFI, contendo as pastas BOOT e OC e seus arquivos.


## Pós-Instalação

5.- Gere sua própria SMBIOS com é como o Serial do Windows, isso para conseguir logar com sua conta Apple ID, baixe o GenSMBIOS https://github.com/corpnewt/GenSMBIOS e execute ´GenSMBIOS.command´ tecle ´2´, e arraste o arquivo "config.plist" encontrado na pasta "OC" precione enter para confirmar, tecle a opção ´3´ Generate SMBIOS, na proxima opção digite o System Product Name que nesse caso para esta EFI é "iMacPro1,1" precione enter 2 vezes clique 6 para confirmar se está tudo certo. Precione Enter e dpois a letra "Q" se fez tudo certom pronto pro uso. Só faça login no APPLE ID, após gerar a SMBIOS corretamente.

6.- Poderá usar o ocvalidate para confirmar tudo antes se está tudo certo antes. Abra o terminal, arraste o ocvalidate para o terminal aberto e em seguida arrate o config.plist também para o terminal e execute. Deverá aparece a seguinte mensagem.

NOTE: This version of ocvalidate is only compatible with OpenCore version 0.9.0!

Completed validating /Volumes/EFI/EFI/OC/config.plist in 6 ms. No issues found.

7.- Use o "hackintool" no icone Power, para corrigir a hibernação, clique na chave de fenda embaixo, digite a senha e confirme. Agora clique na guia "Utilities" pode estar nas setas a Direita escondido ou maximize para ver, localize agora o icone da casa e Disable Gatekeeper digite a senha e pronto pra uso! 


## BUGS CORRIGIDOS

* Adicionado patch para correção de vídeo e áudio, Intel UHD Graphics com HDMI e ajuste de iluminação de tela no notebook e Audio Realtek ALC256 Layout-ID: 11

* Adicionado novas SSDT, DSDT, patchs mais simples

* Adiconado e atualizado Kexts de Audio, Video, Wifi, Bluetooth, Leitor de Cartões, Mapeamento USB, ACPI, NVME, Icone de Bateria, Teclado, Trackpad e outros, também teve a ordem corrigida para o funcionamento correto, mas poderá haver bugs. 

* Tela de boot simplificada, sem icones e desenhos, somente texto, para uma EFI mais leve.

* Adicionado Drivers para boot de sistemas Windows e Linux no Opencore. Atualizados


## BUGS NÃO CORRIGIDOS E CONHECIDOS

* Audio, bug ao iniciar Windows e voltar para o MacOS, o audio pode para de funcionar, necessário desligar e ligar novamente para voltar. Opção de reinciar não resolve, tem que desligar e ligar novamente.

* Trackpad e Teclado se caso não funcionar, use teclado e mouse externo, principalmente de for fazer instalão offline,com a imagem Olarila.

* Wifi Durante instalação Online, podera não funcionar corretamente caso não tenha nada instalado, usar internet via cabo de rede.

* Bug com Balena Etcher, não está gravando, necessário usar root para funcionar atraves do terminal. Nas versões mais antigas, corrigido nas mais recentes.

* Vídeo com apenas 2gb Vram, quando o correto é 4gb Vram.

* Teclas do teclado não funcionado corretamente como as do FN, ou invertidas e trocadas como na tecla " e ' pela tecla de | e \ do lado esquerdo no notebook. 


## Credits

- [Acidanthera](https://github.com/acidanthera) Opencore, Drivers and Kexts
- [RehabMan](https://github.com/RehabMan) Kext
- [OpenIntelWireless](https://github.com/OpenIntelWireless) Kexts
- [Steve Zheng](https://github.com/stevezhengshiqi) Kext
- [Avery Black](https://github.com/1Revenger1) Kext
- [Joshua Wise](https://github.com/jwise) Kext
- [benbaker76](https://github.com/benbaker76) Hackintool and Kext
- [FireWolf](https://github.com/0xFireWolf) Kext
- [Laura Müller](https://github.com/Mieze) Kext
- [CorpNewt](https://github.com/corpnewt) GenSMBIOS, USBmap, Kext, and Others
- [John Davis](https://github.com/Goldfish64) Kext
- [VoodooI2C](https://github.com/VoodooI2C) Kext
- [VoodooSMBus](https://github.com/VoodooSMBus) Kext
- [johnlimabravo](https://github.com/johnlimabravo) Kext
- [Gabriel Luchina](https://github.com/luchina-gabriel) Videos no Youtube, https://www.youtube.com/c/GabrielLuchina Ensinando a criar hackintoshs
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) Instruções para configurações e criações de SSDT, DSDT, e escolha de drivers e Kexts


