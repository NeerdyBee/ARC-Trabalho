# ARC-Trabalho
Instituto Federal Goiano - Campus Ceres
Curso de Bacharelado em Sistemas de Informação / 4º Período
Disciplina de Arquitetura de Redes de Computadores
Aluno: Luis Gabriel Queiroz Carrijo

Documentação do Trabalho - Máquinas Virtuais

Requisitos para o desenvolvimento do trabalho:
    -Sistema Operacional Linux;
    -Para a criação das máquinas virtuais, foi necessária a instalação do software Vagrant;
    -Para o gerenciamento e checagem do funcionamento das máquinas virtuais, foi necessária a instalação do VirtualBox;

Por meio do terminal do sistema Linux, foi usado o comando "vagrant init" para criar o arquivo Vagrantfile, o qual será utilizado para configurar e criar as máquinas virtuais.

Vagrantfile:
    -Primeiramente é iniciado o espaço de configuração das máquinas, determinando a versão a ser utilizada
    -As máquinas criadas são nomeadas de "vm1", "vm2" e "vm3"
    
    VM1:
        -A vm1 atuará como servidor web;
        -É determinada a imagem que ela deverá utilizar para seu sistema, logo em seguida é determinado um IP de rede privada a ela;
        -Para ter seu serviço web, é instalado o Apache atráves das linhas de código que são executadas no sistema em sua criação;
        -Além disso, dentro destas linhas de código é feita a configuração para o Gateway da vm1 estar configurado para o IP da vm3;
        -Por fim, é determinada uma pasta compartilhada entre a máquina física e a vm1, na qual a pasta em que o Vagrantfile por executado estará sincronizada com o diretório /var/www/html na máquina virtual;
    
    VM2:
        -A vm2 atuará como servidor de banco de dados;
        -É determinada a imagem que ela deverá utilizar para seu sistema, logo em seguida é determinado um IP de rede privada a ela;
        -Com intuíto de ter funcionalidades de banco de dados, foi instalado o MySQL através de linhas de códigos;
        -Por fim é feita a configuração para o Gateway da vm1 estar configurado para o IP da vm3;
    
    VM3:
        -A vm3 atuará como Gateway de rede, permitindo que as demais máquinas acessem a rede pública;
        -É determinada a imagem que ela deverá utilizar para seu sistema, logo em seguida é determinado um IP de rede privada a ela;
        -Logo após é configurada a rede pública para a máquina virtual usando o DHCP para designar o IP da rede
        -Por fim são determinados em linhas de código no sistema a funcionalidade da máquina atuar como Gateway entre a rede pública e as demais vms, possibilitando o envio de pacote entre elas
