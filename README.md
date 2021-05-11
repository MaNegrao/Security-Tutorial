<p align="center">
  <a href="https://nmap.org/">
    <img src="logo.png" alt="Logo" width=400 height=230>
  </a>
  <h3 align="center">Guia de uso básico do NMAP - Linux (Ubuntu)</h3>
  <p align="center">NMAP (Network Mapper) é uma ferramenta que oferece a possibilidade de realizar um scan completo em uma rede, obtendo informações sobre hosts e informações de quais portas estão abertas. Além de quais sistemas estão em execução.</p>
</p>
 
## Índice
 
- [Introdução](#Introdução)
- [Diferenciais](#Diferenciais)
- [Algumas Funcionalidades](#Algumas-Funcionalidades)
- [Instalação](#Instalação)
- [Utilização](#Utilização)
- [Exemplo](#Exemplo)
- [Conclusão](#Conclusão)
- [Referências](#Referências)
- [Copyright and Licença](#Copyright-e-Licença)
 
## Introdução
 
O Network Mapper (NMAP) é uma ferramenta gratuita open source utilizada para mapeamento de redes e auditoria de segurança das mesmas. Capaz de detectar serviços e computadores que estão conectados em rede, bem como o gerenciamento de serviços da rede, além do monitoramento de hosts. O NMAP utiliza pacotes IP como meio de determinar quais hosts estão disponíveis na rede, quais serviços os hosts estão oferecendo e qual sistema operacional eles estão rodando, qual o tipo de pacote os filtros usam e inúmeras outras características.
 
## Diferenciais
 
O software possui alguns diferenciais que podem ser citados:
 
- Flexível: Suporta várias técnicas avançadas de mapeamento de rede, utilizando filtros ip, roteadores etc;
- Portável: É possível utilizar na maioria dos sistemas operacionais, como: Microsoft, Linux, MAC, FreeBDS, OpenBDS etc;
- Gratuito: O programa é completamente gratuito e pode ser modificado nos termos da licença;
- Poderoso: O NMAP pode mapear e analisar redes com centenas e até milhares de máquinas.
 
Além de outros diferenciais, como sua documentação completa e os prêmios recebidos como melhor produto de segurança do ano pelo Linux Journal.
 
## Algumas Funcionalidades
 
- Target Specification: Especificação de Alvo, podendo passar como parâmetro o endereço IP, redes, hostnames etc;
- Host Descovery: Descoberta de hosts. Pode listar alvos escaneados, buscar todos os hosts ativos, traçar um caminho para cada host e outras funções;
- Os detection: Ativa a detecção de sistemas operacionais;
- Timing and Performance: Comandos estipular o tempo gasto e a performance dos hosts, timeouts, etc;
- Output: Saídas dos scans, mostrando as interfaces de hosts, rotas, pacotes, etc.
 
## Instalação
 
Para instalar o software no linux em distribuições baseadas no debian, como o Ubuntu 20.04 utilizado neste tutorial, basta seguir os seguintes passos:
 
Você pode instalar utilizando o repositório base do debian utilizando o comando:
 
`sudo apt-get update && sudo apt-get install nmap`
 
Entretanto, a versão do repositório pode estar desatualizada, já que não é mantida pela equipe própria do Nmap.
 
A solução para instalação da versão estável mais recente é baixar o pacote RPM e convertê-lo para um pacote deb. Portanto, o passo a passo é o seguinte:
 
Acesse o [site de download do Nmap](https://nmap.org/download.html) e baixe a última versão para linux RPM.
 
Instale o programa Alien atráves do comando:
 
`sudo apt-get update && sudo apt-get install alien`
 
Acesse a pasta onde foi baixado o arquivo RPM e rode o seguinte comando para gerar a versão .deb:
 
`sudo alien nmap-version.x86_64.rpm`
 
Em seguida, rode o seguinte comando para instalar o Nmap:
 
`sudo dpkg --install nmap-version.x86_64.deb`
 
Após realizar esses passos o nmap já estará instalado em sua máquina.
 
## Utilização
 
O Nmap pode ser utilizado de duas maneiras, via interface gráfica e via linha de comando. A primeira opção pode ser utilizada através da ferramenta Zenmap. Porém, este tutorial utiliza linha de comando para demonstrações.
 
Para executar o Nmap, você deve compor uma linha de comando que irá realizar a função desejada. Todas as possibilidades de chamadas pode ser encontrada na [página guia](https://nmap.org/book/man.html#man-description) da ferramenta. A chamada base para o programa é:
 
`nmap [ <Scan Type> ...] [ <Options> ] { <target specification> }`
 
A partir dessa linha, é possível utilizar todas as funções da ferramenta na linha de comando.
 
Para compor o comando, você deve inserir qual tipo de scan quer fazer, quais os opcionais deseja utilizar e qual o alvo será utilizado. Como no seguinte caso;
 
`nmap -A -T4 scanme.nmap.org`
 
-A é utilizado para detecção do sistema operacional e versão, scripts e a rota até o alvo. -T4 é utilizado para que a execução seja mais rápida. E por fim, scanme.nmap.org é o servidor alvo. A saída da execução é a seguinte:
 
```
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.20s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 993 closed ports
PORT      STATE    SERVICE    VERSION
22/tcp    open     ssh        OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   1024 ac:00:a0:1a:82:ff:cc:55:99:dc:67:2b:34:97:6b:75 (DSA)
|   2048 20:3d:2d:44:62:2a:b0:5a:9d:b5:b3:05:14:c2:a6:b2 (RSA)
|   256 96:02:bb:5e:57:54:1c:4e:45:2f:56:4c:4a:24:b2:57 (ECDSA)
|_  256 33:fa:91:0f:e0:e1:7b:1f:6d:05:a2:b0:f1:54:41:56 (ED25519)
23/tcp    filtered telnet
25/tcp    filtered smtp
26/tcp    filtered rsftp
80/tcp    open     http       Apache httpd 2.4.7 ((Ubuntu))
|_http-title: Go ahead and ScanMe!
9929/tcp  open     nping-echo Nping echo
31337/tcp open     tcpwrapped
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
 
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 20.41 seconds
```
 
## Exemplo
 
`nmap -v scanme.nmap.org`
 
Esse comando escaneia todas as portas TCP reservadas na máquina scanme.nmap.org. O -v funciona para se obter um resultado detalhado. A saída do comando é a seguinte:
 
```
Starting Nmap 7.70 ( https://nmap.org ) at 2021-05-11 14:35 -03
Initiating Ping Scan at 14:35
Scanning scanme.nmap.org (45.33.32.156) [2 ports]
Completed Ping Scan at 14:35, 0.20s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 14:35
Completed Parallel DNS resolution of 1 host. at 14:35, 0.65s elapsed
Initiating Connect Scan at 14:35
Scanning scanme.nmap.org (45.33.32.156) [1000 ports]
Discovered open port 80/tcp on 45.33.32.156
Discovered open port 22/tcp on 45.33.32.156
Discovered open port 9929/tcp on 45.33.32.156
Discovered open port 31337/tcp on 45.33.32.156
Completed Connect Scan at 14:35, 8.37s elapsed (1000 total ports)
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.20s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 993 closed ports
PORT      STATE    SERVICE
22/tcp    open     ssh
23/tcp    filtered telnet
25/tcp    filtered smtp
26/tcp    filtered rsftp
80/tcp    open     http
9929/tcp  open     nping-echo
31337/tcp open     Elite
 
Read data files from: /usr/bin/../share/nmap
Nmap done: 1 IP address (1 host up) scanned in 9.53 seconds
```
 
## Conclusão
 
A ferramenta é completa e oferece uma ampla gama de funcionalidades. Este tutorial apresentou uma parte mínima da ferramenta, apenas para demonstração e apresentação da mesma. É indicado que, para o entendimento completo da ferramenta e sua utilização segura, a documentação deve ser consultada.
 
## Referências
 
Todas as instruções utilizadas neste tutorial foram desenvolvidas com base na documentação da ferramenta disponível no site nmap.org.
 
## Copyright e Licença
 
Desenvolvido por Matheus Negrão, com base na documentação disponibilizada pela equipe do nmap em nmap.org. Sob a licença [MIT License](https://reponame/blob/master/LICENSE).
