# SIP e prática sipp

Neste repositório você irá aprender a Instalar e configurar o ambiente, configurar extensões e a realizar análise de log do SIP em tempo real.

## O Que é o Asterisk? 

* O Asterisk é um servidor de Voz sobre o IP (VoIP).

* É Utilizado para estabelecer e controlar chamadas telefônicas entre pontos e extremidade de telecomunicações, como aparelhos telefônicos comuns, destinos na rede telefônica pública comutada (PSTN) e dispositivos ou serviços de voz sobre protocolo Internet Redes (VoIP).

* Uma Observação interessante é que seu nome deriva do símbolo asterisco (*) de um sinal usado na discagem por tom (DTFM).

* Pode trabalhar com um conjunto de interfaces de hardware de telefonia e aplicativos de rede adequados.

* O Asterisk é gratuito e de código aberto.

## O Que é o FreePBX? 

* O FreePBX é uma interface gráfica do usuário (GUI) de código aberto (Open Source) baseada em Web que gerencia o Asterisk.

* Ajuda e facilia a configuração e gerenciamento do Asterisk

* É também uma comunidade de desenvolvedores e colaboradores que dedicam seu trabalho a tornar o software e complicado do sistema telefônico fácil de usar e funcional.

* Gratuito :)

## O Que será aplicado no cenário? 

Após configurado o servidor, poderá ser realizado as ligações SIP entre o hardphone ou softphone.

![SIP RTP drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/4a8b08d7-5df0-4555-9d1a-467ee92013fb)

## Requisitos

* Um Computador ( Mínimo 4 GB RAM )

* Rede com roteador

* Opcional: Telefone IP ( Hardphone )

## Topologia 

![Diagrama sem nome drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/7f70caf6-245f-41aa-bc98-7169ce7c8f59)

## Instalação e configuração do Asterisk com FreePBX

## VirtualBox

* É um Hipervisor, ou seja, possibilita criar ambientes virtuais para instalação de outros sistemas.

* Permite que um sistema operacional seja instalado e utilizado dentro de outro sistema, assim como seus respectivos softwares, mas compartilhando fisicamente o mesmo hardware.

Para baixar o Hipervisor, basta acessar o site oficial [Clicando aqui](https://www.virtualbox.org).

![virtualbox](https://github.com/edunando/SIP-na-pratica/assets/88983626/8e5e2967-3538-48da-924c-ca15da2332c3)

## FreePBX

* Para baixar o FreePBX vamos acessar a página oficial e realizar o download da ISO. [Clique aqui para acessar](https://www.freepbx.org)

![FreePBX](https://github.com/edunando/SIP-na-pratica/assets/88983626/04e15cbd-d939-4f64-8f2d-7ffb3e289ea1)

Após o Download vamos realizar a instalação no nosso Hipervisor selecionado, nesse caso o VirtualBox.

* Configuração da Máquina Virtual do FreePBX

![FreePBXhomepage](https://github.com/edunando/SIP-na-pratica/assets/88983626/66f6e789-d036-4c78-9fb0-4ff7c22a3c76)

![ConfPBX](https://github.com/edunando/SIP-na-pratica/assets/88983626/5d14bb87-6001-4616-9639-5f9a285aa0e6)

No momento da instalação você poderá utilizar uma versão do FreePBX de sua preferência, porém, a utilizada nesse momento foi o FreePBX 16 ( Asterisk 18 ). No momento da instalação lembre-se de configurar corretamente a senha de root para logar.




