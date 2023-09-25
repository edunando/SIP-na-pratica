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

![ConfPBX](https://github.com/edunando/SIP-na-pratica/assets/88983626/5d14bb87-6001-4616-9639-5f9a285aa0e6)

* No momento da instalação você poderá utilizar uma versão do FreePBX de sua preferência, porém, a utilizada nesse momento foi o FreePBX 16 ( Asterisk 18 ). No momento da instalação lembre-se de configurar corretamente a senha de root para logar.

![FreePBXhomepage](https://github.com/edunando/SIP-na-pratica/assets/88983626/66f6e789-d036-4c78-9fb0-4ff7c22a3c76)

* IPs do Cenário
  
![ip drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/46f87112-5d2c-437f-9eb4-9ab39342fe66)

Lembre-se de setar corretamente o IP do Gateway e o ip do Servidor para evitar problemas de configuração.

* Portas que serão Utilizadas
  
![Portas drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/fe4db712-d1b4-4593-bf26-9f6110f02aec)

* Tela inicial de Setup

![Tela inicial de Setup](https://github.com/edunando/SIP-na-pratica/assets/88983626/2515bb58-5001-47fd-ac8d-88a8664b1351)

Inicialmente vamos criar nosso usuário administrativo, senha e nome do servidor.

* Menu Principal

![Menu Principal](https://github.com/edunando/SIP-na-pratica/assets/88983626/3be658c1-1072-456d-8708-44b0eaf7be5d)

## Ativando o FreePBX

Inicialmente você deve Acessar na tela inicial a parte de Admin Configuracion onde você poderá estar realizando tanto a ativação do Servidor quanto o Firewall pré-instalado no próprio FreePBX. Após a configuração inicial de Firewall e Linguagem, teremos acesso as principais funcionalidades de configuração e monitoramente do servidor.

![Server](https://github.com/edunando/SIP-na-pratica/assets/88983626/fcb4332d-64cf-4fdb-9671-a1af2888d390)


Apesar de ser um módulo gratuito, é necessário que a instalação do FreePBX seja ativa. Para realizar tal procedimento vamos acessar no menu superior esquerdo Admin --> System Admin --> Activation

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/6caff9b5-bc4f-48e7-b656-0e7865f648a7)

Após a ativação será necessário preencher alguns dados seus no formulário de ativação. Após o preenchimento dos dados a Ativação terá sido um sucesso!

## Configurando Módulo de rede

Como dito anteriormente é necessário que as configurações de rede estejam configuradas corretamente para tudo funcionar perfeitamente. Para darmos continuidade ao processo de configuração do cenário vamos acessar Network Configuration que fica localizado no canto diretio da tela nas configurações administrativas, onde iremos mudar de DHCP para Static. Após Verificar que todas as configurações estão corretas basta salvar e aplicar, após isso o servidor será reiniciado e as configurações estarão setadas!

![Network Configuration](https://github.com/edunando/SIP-na-pratica/assets/88983626/81837bfc-c4d9-45d7-844f-df6d183be881)

## Configurando Firewall

Para configurarmos corretamente o nosso firewall do FreePBX é necessário acessar novamente as configurações administrativas após isso vamos na aba "Connectivity" --> Firewall
Vamos selecionar a interface desejada, no caso a eth0 e deixar selecionado a opção Local ( Local Trusted Traffic ) como na imagem abaixo. Vale ressaltar de além de selecionnar a opção de update interface todas as configurações devem ser aplicadas senão não serão efetivadas, para isso selecionar a opção que fica no canto superior direito da tela Apply Config.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/fe7b36a4-5ce5-4de4-8b7e-107612d2f787)


## Configurando Extensões Asterisk FreePBX

* Uma extensão geralmente se refere a uma linha interna conectada ao PBX ( VoIP ou não ), e que não possui uma linha externa separada.

* Permite que as empresas compartilhem algumas linhas externas entre muitos funcionários, pois nem todo mundo fará chamadas externas ao mesmo tempo.

* Permite que os usuários do mesmo escritório liguem um para o outro escritório discando ramais de poucos dígitos em vez de procurar o número de telefone completo ( vários dígitos ).

* Geralmente discagem por ramal é de quatro dígitos. Mas isso NÃO é regra, pode ter como uso menos ou mais dígitos.

* Exemplo de Extensão

![PEPBSIP drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/29e91360-d26b-49d9-b631-56bf889c0b92)

* Voip e NAT

* Os Protocolos VoIP convencionais são projetados de modo que cria um problema no tráfego de VoIP que passa pelo NAT.

* Os protocolos de VoIP convencionais lidam apenas com a sinalização de uma conexão.

* O Tráfgo de áudio é tratado por outro protocolo e, para piorar, a porta na qual o tráfego de áudio é enviado é aleatória.

* O Roteador NAT pode ser capaz de lidar com o tráfego de sinalização, mas não tem como saber que o tráfego de áudio está relacionado à sinalização e, portanto, deve ser passado para o mesmo dispositivo ao qual o tráfego de sinalização é transmitido.

* Como resultado, o tráfego de áudio não é traduzido corretamente entre os espaços de endereço. Inicialmente, tanto quem fez a chamada quanto para quem recebe parecerá bem. O interlocutor verá o identificador de chamada, o telefone tocará enquanto na outra extremidade.

* Quando a outra pessoa chamada atender o telefone não ouvirá a parte chamada ( áudio unidirecional ) e também não poderia ouvir nada (sem áudio). A questão do NAT transversaç é um grande problema para a implantação do VOIP. O Problerma não é trivial e não há soluções simples.

![sip-exempl drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/0cf43a9f-b043-4134-a14f-5f408c3d8588)

## Implementação Sip no Asterisk: CHAN_PJSIP

* É uma biblioteca de comunicação multimídia de código aberto e gratuita que implementa protocolos como SIP, SDP, RPT.

* Combina o Protocolo de Sinalização ( SIP ) com a estrutura multimídia e a funcionalidade do NAT na API de comunicação multimídia de alto nível que é portátil e adequada para praticamente qualquer tipo de sistema, desde desktop, sistemas embarcados a aparelhos móveis.

* Fornece ao desenvolvedor, tudo o que precisa para criar um aplicativo de comunicação multimídia em tempo real. Todos os três componentes principais do aplicativo multimídia em tempo real, ou seja, sinalização, recursos de mídia e passagem NAT

![CHAN PJSIP](https://github.com/edunando/SIP-na-pratica/assets/88983626/d3e6f8cb-0f64-4c4d-b206-7e4b0bf466f6)


* Extensão do cenário
  
![Extensaocenario drawio](https://github.com/edunando/SIP-na-pratica/assets/88983626/f5a78e48-75e9-4392-9c72-d1d679d7f9d6)


## Criando as Extensões no FreePBX

* Para criarmos nossas primeiras extensões vamos precisar acessar o Menu principal --> Applications --> Extensions onde iremos nos deparar com a seguinte página.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/30995031-3096-4c53-8bfc-6d29925492c7)

* Vamos selecionar a Opção Add Extension e selecionar a opção "Add New SIP [chan_pjsip] Extension"

* Após Acessar a janela de criação de extensão devemos númerar a extensão e salvar o Secret onde a mesma é a senha da extensão que será criada.
  
  ![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/227009b4-2e29-4b98-8681-c00617421b08)

* Após isso irei repetir o mesmo processo para criar as nossas duas extensões do cenário do tipo PJSIP. Após a configuração realizada Selecionar a Opção Apply Config

  ![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/24cb08bd-2fd9-42b1-8b13-3b78ec9115f1)


## Configurando os Softphones

* Como no momento não possuo em mãos um hardphone, irei continuar a configuração com dois Softphones um no meu desktop ( 5001 ) e outro em um aparelho celular ( 5002 ). O Software que estarei utilizando no desktop tanto para o softphone é o  3CX que você pode estar baixando ele diretamente no site oficial deles ![Clicando aqui](https://www.3cx.com/voip/softphone/) e no aparelho celular estarei utilizando o ZOIPER que pode ser encontrado na loja de seu dispositivo.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/d9ac0b72-22a0-4991-adc8-d3e80603221f)

* Após o Download vamos estar adicionando as nossas extensões aos Profiles, de inicio vamos configurar a nossa primeira extensão a 5001.
  
![Configsoftphone](https://github.com/edunando/SIP-na-pratica/assets/88983626/33a9ee8c-b320-4b61-b009-f7283596958b)

* Após a configuração da primeira extensão estarei repetindo o mesmo processo para a segunda sendo o 5002.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/2c4f2e16-488c-4467-9b25-6a7535cd868a)

* Após isso estarei realizando a configuração no Zoiper.
  
![Imagem do WhatsApp de 2023-09-24 à(s) 23 17 48](https://github.com/edunando/SIP-na-pratica/assets/88983626/a01dabdf-6d5c-447a-be88-9c4be24d1f20)

* Após as configurações, os softphones já estão funcionais e poderão ser utilizados com sucesso!!

* Softphone Zoiper no Smarthphone

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/170c455e-1689-4ddb-8906-945887eb4604)

* 3Cx no Computador

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/991e5822-fc22-4e53-895c-a227f53c1fbd)


## Extras - Visualização de Logs 

* Para realização da visualização dos logs vamos estar utilizando o sngrep. Para utilizar a ferramente é bem simples, basta digita na CLI do seu servidor, após isso irá aparecer os logs atuais.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/861af253-3421-4983-8834-f07c951e69d3)

* Vamos selecionar um e verificar todo o funcionamento detalhadamente.

![image](https://github.com/edunando/SIP-na-pratica/assets/88983626/55d33797-0a9c-4761-aeb1-226dd3ef456c)

