## Projeto Integrador III-A - Redes de Computadores

Bem vindos ao repositório de trabalho do PI III-A

Após este Projeto Integrador o aluno deverá ser capaz de organizar soluções para monitoramento de informações em redes de computadores complexas, como a Internet das Coisas. Os alunos serão levados a se apropriar de conceitos e funcionalidades de plataformas de amplo uso no cenário nacional e internacional, bem como explorar protocolos que viabilizem a implementação prática de soluções para monitoramento e análise de dados coletados de ambientes computacionais interconectados pela Internet.

Neste **[link](https://docs.google.com/document/d/1zdyfHIcCNcf-rySs3LN2_LurPBLUwJroQaxFDrOZwx0/edit)** está disponível o seu Plano de Execução.

### Professores Responsáveis

* Adenauer Yamin - adenauer.yamin at ucpel.edu.br
* Rogério Albandes - rogerio.albandes at ucpel.edu.br


### Equipe Acadêmica

Os grupos devem ser compostos com o total de integrantes variando de 1 a 3.

* **Grupo 1:** Natanaele Barros Machado e Emerson Barbosa De Medeiros
* **Grupo 2:** Anderson Fernandes Moreira e Diogo Bitencourt Neuenfeld
* **Grupo 3:** Dionathan Moraes Fuhrmann e Luciano Couto Da Silva
* **Grupo 4:** Ranieri Martins Da Silva e Rodrigo Dos Santos Olmos
* **Grupo 5:** Cinthia Scheunemann

Abaixo está a indicação da Plataforma IoT sob a responsabilidade de cada grupo.

 
### Primeiro Encontro Síncrono - 26/03/2022

#### Visão Geral da IoT
  * [Slides Introdutórios](http://olaria.ucpel.edu.br/materiais/lib/exe/fetch.php?media=internet-das-coisas-iot.pdf)

#### História do Unix
* [Site 1](https://www.levenez.com/unix/), [Site 2](https://en.wikipedia.org/wiki/Timeline_of_operating_systems), [Site 3](https://lcomlinux.wordpress.com/a-historia-do-linux/), [Site 4](https://distrowatch.com/)
* [Padrão POSIX](https://pt.wikipedia.org/wiki/POSIX)

#### Explorando Máquinas Virtuais para Instalação de uma Distribuição Linux

Para uso do Bash, abaixo algumas opções:

* Emprego de um Gerenciador de Máquinas Virtuais + Distribuição Linux: 
   * Virtualizador sugerido: [Virtual Box](https://www.virtualbox.org/) instalar também o Extension Pack
   * Distribuição sugerida: [Linux Mint](https://linuxmint.com/)
* Explorando o [WSL](https://docs.microsoft.com/pt-br/windows/wsl/about)

#### Atualizando o sistema operacional (Sistemas com base no Debian)
* sudo su \-
* apt-get update
* apt-get upgrade
* apt-get autoremove (se necessário)

#### Instalando um software por apt-get via terminal
* Atualizar o sistema operacional (vide item acima)
* Como root:
  * apt-cache search \<parte do nome ou funcionalidade do possível pacote\>
  * apt-get install \<nome do pacote\>



  * Explorando Scripts Bash no Linux
    * Guia Foca Linux - [Site](https://guiafoca.org/)
    * Livros sobre Bash Scripts - [Diretório](https://drive.google.com/open?id=0B2INSZz1E5TlVWdkVFM0OUxKXzA)
    * Exemplos de Scripts:
      * [Filtro CPU e Memória](http://olaria.ucpel.edu.br/materiais/doku.php?id=script-filtro-informacoes)
      * [Captura Informações Dinâmicas](http://olaria.ucpel.edu.br/materiais/lib/exe/fetch.php?media=script-cpu-dinamico.sh.zip)
  * Para tornar executável um Script utilizar no terminal o comando **chmod 755 nome-do-programa.sh**
  * Para executar utilizar **./nome-do-programa.sh**

#### Para monitorar a ocupação de CPU utilizar um programa para gerar carga sintética, como o abaixo escrito em Bash:

~~~
while [ 1 ]
do
a=7.11/6.79
done
~~~


  * Para tornar executável utilizar no terminal o comando **chmod 755 nome-do-programa.sh**
  * Para executar utilizar **./nome-do-programa.sh**

#### Plataformas para Monitoramento no Cenário da IoT

* [Principais Alternativas Dispníveis](http://olaria.ucpel.edu.br/materiais/doku.php?id=plataformas_nuvem_iot)
* Plataformas selecionadas para os grupos. A seleção teve como critério ter a possibilidade de uso sem custo:
  * **Grupo 1:** Konker http://www.konkerlabs.com/
  * **Grupo 2:** Thingsboard https://thingsboard.io 
  * **Grupo 3:** ThingSpeak https://thingspeak.com/.
  * **Grupo 4:** Ubidots https://ubidots.com/stem/ 
  * **Grupo 5:** Tago https://tago.io/
     
 #### Transmitindo Informações Sensoriadas do Meio para um Servidor
  * Conceitos
    * [Protocolo MQTT - Material IBM](https://www.ibm.com/developerworks/br/library/iot-mqtt-why-good-for-iot/index.html)
    * [Protocolo MQTT - Material Curto Circuito](https://www.curtocircuito.com.br/blog/introducao-ao-mqtt/)
    * [Slides sobre MQTT - Material UFC](https://pt.slideshare.net/MaurcioMoreiraNeto/protocolo-mqtt-redes-de-computadores)
  * Plataformas de Software
    * [Mosquitto da Eclipse Foundation](https://mosquitto.org)
    * [Brokers MQTT gratuitos e pagos para utilizar em projetos da IoT](https://mntolia.com/10-free-public-private-mqtt-brokers-for-testing-prototyping/)
  * Brokers MQTT publicos:
    * https://mntolia.com/10-free-public-private-mqtt-brokers-for-testing-prototyping/

#### Implementação Realizada

  * Broker MQTT selecionado para os testes: 
    * URL: broker.hivemq.com
    * Porta: 1883

* Script Bash utilizando MQTT para monitorar CPU
  * O Código empregado está disponível neste [link](https://github.com/adenauery/Redes-PI3/blob/master/publica-emqx.sh)
  * Para **recber os valores publicados** pelo script utilizar: **mosquitto_sub -h broker.hivemq.com -t pi3a** (**desativado no momento**)
  * As publicações acontecem de minuto em minuto

* Abaixo um dashbord feito para o Projeto Integrador III - A, que também recebe por MQTT os valores publicados pelo script:
  * pi.exehda.org:3000/  (**desativado no momento**)
  * usuário: pi3a  
  * password: luz@azul#pi

Este dahsboard foi feito utilizando o Framework Grafana e o Banco de Dados PostgreSQL 

### Entrega (Relatório) Parcial:

  * O período de entrega do Relatório Parcial é de 28/03 até 04/04 às 23:59h, via a Plataforma A
  * A Entrega Parcial, que contempla 40% da nota do projeto integrador, irá consistir de um Relatório Parcial compreendendo os seguintes pontos: (a) uma descrição dos principais aspectos e funcionalidades referentes a uma plataforma, a ser selecionada pelo aluno, empregada no monitoramento de informações na Internet das Coisas (IoT); (b) instalação e testes de um script bash para monitoramento, que publique em um Broker MQTT. O Relatório Parcial deverá ser entregue empregando a Plataforma A.


 
### Segundo Encontro Síncrono - 09/04/2022
#### Checklist da aula
- [ ] Instalar Linux ou VM com linux
- [ ] Instalar Phyton
- [ ] Instalar editor de texto preferido
- [ ] Criar a conta na plataforma selecionada para o grupo
- [ ] Criar conta no GitHub (opcional)

### To do 
- [ ] Script em shell para gerar carga na CPU ou similar
- [ ] Programa em Python para a medida da CPU ou similar
- [ ] Publicação na plataforma definida para o grupo
- [ ] Realizar push no GitHub (opcional)

### Entrega (Relatório) Final:
  * O período da Entrega Final é de 25/04 até 29/04 às 23:59h, via a Plataforma A.
  * A Entrega Final, que contempla 60% da nota do projeto integrador, irá consistir da entrega de um Relatório Final que descreva os procedimentos realizados para desenvolvimento de uma aplicação empregando protocolos e uma linguagem de programação para monitoramento de equipamentos conectados em uma rede. As informações monitoradas deverão ser postadas na Plataforma para monitoramento na IoT selecionada pelo grupo. Juntamente com o Relatório Final deverá ser também entregue um vídeo que trate do apresentado tanto no Relatório Parcial, como no Final. O vídeo deverá ser disponibilizado na forma de um link presente no Relatório Final. O Relatório final deverá ser entregue empregando a Plataforma A.

#### Protocolo Git
  * Site de referência - [Fast Version Control ...](https://git-scm.com/)
  * Criar conta no GitHub: https://github.com/
  * [Alternativas ao GitHub](https://pt.wikiversity.org/wiki/Github_x_Gitlab_x_Bitbucket)
  * Utilizando o GitHub - [Tutorial 1](https://rogerdudler.github.io/git-guide/index.pt_BR.html), [Tutorial 2](https://www.hostinger.com.br/tutoriais/comandos-basicos-de-git/), [Tutorial 3](https://gist.github.com/leocomelli/2545add34e4fec21ec16)
  * Exercitar a sintaxe do Markdown: [Tutorial 1](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown)

  * Comandos selecionados:
    * git help
    * git clone \<URL provida pelo GitHub\>
    * git config --global user.name "Leonardo Comelli"
    * git config --global user.email leonardo@software-ltda.com.br
    * git add meu_arquivo.txt (para adicionar todos os arquivos git add .)
    * git rm meu_arquivo.txt
    * git commit meuarquivo.txt -m "minha mensagem de commit"
    * git push (para enviar arquivos ao diretório remoto)
      * a primeira vez utilizar git push -u origin master
    * git pull (para buscar arquivos diretório remoto)

 
 ### Instalando ThingsBoard em equipamento local
   * [Instalando o ThingsBoard utilizando Dockers](https://thingsboard.io/docs/user-guide/install/docker/?ubuntuThingsboardQueue=inmemory)
   * [Instalando o Docker no Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-pt)
   * [Instalando o Docker-Composer no Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-pt)
 
 
<!-- ESTA PARTE ESTÁ COMENTADA
    

  * **Ferramentas Open Source para Análise Estatística de Grandes Volumes de Dados:**     
      * https://pt.wikipedia.org/wiki/Scilab (Open Source) similar ao [Matlab](https://pt.wikipedia.org/wiki/MATLAB)
      * Python Pandas: [Site 1](https://harve.com.br/blog/programacao-python-blog/pandas-python-vantagens-e-como-comecar/) - [Site 2](https://insightlab.ufc.br/10-funcoes-mais-usadas-para-manipular-dataframes-no-pandas/)

  * **Exemplo de Uso do LaTeX**
    * [Exemplo de Texto](https://www.overleaf.com/read/cqtvqphcvnyd)
    * [Exemplo de Apresentação](https://www.overleaf.com/read/dwthrxtnchbb)
    * [Dicas sobre o uso de LaTeX](http://olaria.ucpel.edu.br/latex/)

  * **Exemplo de Apresentação explorando o Google Docs**
    * [Exemplo de Apresentação](https://docs.google.com/presentation/d/1CaY3PK5XJZ73Zojp6r_omlfoj-3kg-suxOLtwOEI6rg/edit?usp=sharing)


#### Protocolo Git
  * Site de referência - [Fast Version Control ...](https://git-scm.com/)
  * Criar conta no GitHub: https://github.com/
  * [Alternativas ao GitHub](https://pt.wikiversity.org/wiki/Github_x_Gitlab_x_Bitbucket)
  * Utilizando o GitHub - [Tutorial 1](https://rogerdudler.github.io/git-guide/index.pt_BR.html), [Tutorial 2](https://www.hostinger.com.br/tutoriais/comandos-basicos-de-git/), [Tutorial 3](https://gist.github.com/leocomelli/2545add34e4fec21ec16)
  * Exercitar a sintaxe do Markdown: [Tutorial 1](https://docs.pipz.com/central-de-ajuda/learning-center/guia-basico-de-markdown)

  * Comandos selcionados:
    * git help
    * git clone \<URL provida pelo GitHub\>
    * git config --global user.name "Leonardo Comelli"
    * git config --global user.email leonardo@software-ltda.com.br
    * git add meu_arquivo.txt (para adicionar todos os arquivos git add .)
    * git rm meu_arquivo.txt
    * git commit meuarquivo.txt -m "minha mensagem de commit"
    * git push (para enviar arquivos ao diretório remoto)
      * a primeira vez utilizar git push -u origin master
    * git pull (para buscar arquivos diretório remoto)
 

  * Empregando uma linguagem de programação com MQTT
  
    * [Explorando o uso de MQTT em Programas Python](https://fazbe.github.io/Usando-o-paho-mqtt-para-Python/)

#### Comunicando com um Broker MQTT utilizando Python

No link a seguir, dicas de como instalar e utilizar o Python: **[Python Brasil](https://python.org.br/)**

  * A linguagem Python
    * [Aprendendo Python](https://wiki.python.org.br/AprendaProgramar)
    * [Integrando Bash e Python](http://olaria.ucpel.edu.br/materiais/doku.php?id=integrando-bash-python)

##### Procedimento de Subscrição
~~~
# Cliente Python para subscrever em um Broker MQTT
#
# Para instalar o paho-mqtt use o comando pip install paho-mqtt
import paho.mqtt.client as mqtt

# Retorno quando um cliente recebe um  CONNACK do Broker, confirmando a subscricao
def on_connect(client, userdata, flags, rc):
    print("Conectado, com o seguinte retorno do Broker: "+str(rc))

    # O subscribe fica no on_connect pois, caso perca a conexão ele a renova
    # Lembrando que quando usado o #, você está falando que tudo que chegar após a barra do topico, será recebido
    client.subscribe("PI-3A/#")

# Callback responsavel por receber uma mensagem publicada no tópico acima
def on_message(client, userdata, msg):
    print(msg.topic+" "+str(msg.payload))

client = mqtt.Client()
client.on_connect = on_connect
client.on_message = on_message

# Define um usuário e senha para o Broker, se não tem, não use esta linha
# client.username_pw_set("USUARIO", password="SENHA")

# Conecta no MQTT Broker
client.connect("mqtt.eclipse.org", 1883, 60)

# Blocking call that processes network traffic, dispatches callbacks and
# handles reconnecting.
# Other loop*() functions are available that give a threaded interface and a
# manual interface.
# Inicia o loop
client.loop_forever()
~~~

##### Procedimento de Publicação
~~~
# Ensures paho is in PYTHONPATH
import context
# Importa o publish do paho-mqtt
import paho.mqtt.publish as publish

# Publica
publish.single("PI-3A", "Olá Mundo!", hostname="mqtt.eclipse.org")
~~~

* **Entrega (Relatório) Final:**
    * O período da Entrega Final é de 25/04 até 29/04 às 23:59h, via a Plataforma A
    * A Entrega Final, que contempla 60% da nota do projeto integrador, irá consistir da entrega de um Relatório Final que descreva os procedimentos realizados para desenvolvimento de uma aplicação empregando protocolos e uma linguagem de programação para monitoramento de equipamentos conectados em uma rede. As informações monitoradas deverão ser postadas na Plataforma para monitoramento na IoT selecionada pelo grupo. Juntamente com o Relatório Final deverá ser também entregue um vídeo que trate do apresentado tanto no Relatório Parcial, como no Final. O vídeo deverá ser disponibilizado na forma de um link presente no Relatório Final. O Relatório final deverá ser entregue empregando a Plataforma A.


-->
