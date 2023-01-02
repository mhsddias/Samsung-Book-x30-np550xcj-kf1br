# SAMSUNG-BOOK-X30-NP550XCJ-KF1BR
### EFI OC HACKINTOSH VENTURA
EFI Baseado no Opencore 0.8.7

## --OBSERVAÇÕES IMPORTANTES--

* Baixe a imagem do "Ventura 13.1 with EFI folder for chipset series 300, 400 and 500" no site Olarila:
https://www.olarila.com/topic/6278-hackintosh-and-macintosh-olarila-vanilla-images-macos-installer/

* Precisa de um pendrive com 16gb ou mais, teclado e mouse USB externo;

* Use o Balena Etcher para gravar a imagem no pendrive;
https://www.balena.io/etcher/

* Crie uma partição que deseje apagar no formato FAT onde deseja instalar o MacOS;

* Após instalação substitua a EFI do pendrive pela aqui baixada usando o ESP mounter pro, encontrado na imagem baixada no site olarila e gravado no pendrive ou pelo próprio site olarila.
https://www.olarila.com/files/Utils/ESP%20Mounter%20Pro.app_v1.9.1.zip

## --BUGS CORRIGIDOS--

* Adicionado patch para correção de vídeo e áudio, Intel UHD Graphics com HDMI e ajuste de iluminação de tela no notebook e Audio Realtek ALC256 Layout-ID: 11

* Adicionado algumas SSDT e DSDT e patchs

* Adicionado Kext de Audio, Video, Wifi, Bluetooth, Leitor de Cartões, Mapeamento USB, Icone de Bateria e Teclado.


## --BUGS NÃO CORRIGIDOS E CONHECIDOS--

* Audio bug ao iniciar Windows e voltar para o MacOS, para de funcionar, necessário desligar e ligar novamente para voltar.

* Trackpad não funcionando, problemas no I2C e GPIO, ou kexts, solução usar Mouse USB.

* Vídeo com apenas 2gb Vram, quando o correto é 4gb Vram.
