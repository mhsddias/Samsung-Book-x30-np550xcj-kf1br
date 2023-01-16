# SAMSUNG BOOK X30 NP550XCJ-KF1BR
### EFI OC HACKINTOSH VENTURA ATUALIZADA
EFI Baseado no Opencore 0.8.8

## OBSERVAÇÕES E RECOMENDAÇÕES IMPORTANTES

* Baixe os arquivos e imagem do oficiais do mac atraves do ´macrecovery´ app encontrado diretamente do pacote OpenCore pelo link https://github.com/acidanthera/OpenCorePkg, vá em release e baixe a ultima versão. Irá precisar usar também do python para baixar e criar um pendrive bootável use o link https://www.python.org/downloads/ e baixe app essa instalação irá precisar de internet, ou baixe a imagem off-line pronta não-oficial, porém, não muito recomendado, pelo site https://www.olarila.com/topic/6278-hackintosh-and-macintosh-olarila-vanilla-images-macos-installer/ e baixe a imagem do "Ventura 13.1 with EFI folder for chipset series 300, 400 and 500" no site Olarila: https://www.olarila.com/topic/6278-hackintosh-and-macintosh-olarila-vanilla-images-macos-installer/

* Para imagem online precisará de 2gb em um pendrive e para a off-line de um pendrive com 16gb ou mais, 

* Para Imagem baixada no olarila percisará de teclado e mouse USB externo; ou mude a EFI para a que está disponivel aqui.

* Use o Balena Etcher para gravar a imagem no pendrive;
https://www.balena.io/etcher/

* Crie uma partição que deseje apagar no formato FAT onde deseja instalar o MacOS;

* Após instalação substitua a EFI do pendrive pela aqui baixada usando o ESP mounter pro, encontrado na imagem baixada no site olarila e gravado no pendrive ou pelo próprio site olarila.
https://www.olarila.com/files/Utils/ESP%20Mounter%20Pro.app_v1.9.1.zip

Após Instalação faça e gere sua própria SMBIOS para conseguir logar com sua conta Apple ID, baixe o GenSMBIOS https://github.com/corpnewt/GenSMBIOS e execute ´GenSMBIOS.command´ tecle ´3´, na proxima opção precisa usar o System Product Name que nesse caso para esta EFI é iMacPro1,1 e altere os valores no arquivo ´Config.plist´ dessa EFI, use o ´Propertree´ e altere os valores em PlatformInfo/Generic.`

## BUGS CORRIGIDOS

* Adicionado patch para correção de vídeo e áudio, Intel UHD Graphics com HDMI e ajuste de iluminação de tela no notebook e Audio Realtek ALC256 Layout-ID: 11

* Adicionado novas SSDT e DSDT e patchs

* Adicionado Kext de Audio, Video, Wifi, Bluetooth, Leitor de Cartões, Mapeamento USB, Icone de Bateria e Teclado e outros, também teve a ordem corrigida.

* Trackpad funcionando, problemas no I2C e GPIO corrigido, kexts ordenadas, mas caso ainda haja algum problema poderá usar um Mouse USB.


## BUGS NÃO CORRIGIDOS E CONHECIDOS

* Audio, bug ao iniciar Windows e voltar para o MacOS, para de funcionar, necessário desligar e ligar novamente para voltar.
Opção de reinciar não resolve, tem que desligar e ligar novamente.

* Bug com Balena Etcher, não está gravando, necessário usar root para funcionar atraves do terminal.

* Vídeo com apenas 2gb Vram, quando o correto é 4gb Vram.

## BUG RARO

* Caso o notebook fique com tela preta e não apareça nada na tela, mesmo após o deligamento manual forçado do notebook, segurando o botão de ligar por 10 segundos, deverá descarregar totalmente o notebook para ligar novamente.
