<p align="center">
  <a href="https://nmap.org/">
    <img src="logo.png" alt="Logo" width=400 height=230>
  </a>
  <h3 align="center">Guia de uso básico do NMAP - Linux (Ubuntu)</h3>
  <p align="center">NMAP (Network Mapper) é uma ferramenta que oferece a possibilidade de realizar um scan completo em uma rede, obtendo informações sobre hosts e informações de quais portas estão abertas. Além de quais sistemas estão em execução.</p>
</p>

## Indice

- [Introdução](#Introdução)
- [Diferenciais](#Diferenciais)
- [Algumas Funcionalidades](#Algumas-Funcionalidades)
- [Instalação](#Instalação)
- [Utilização](#Utilização)
- [Exemplo](#Exemplo)
- [Conclusão](#Conclusão)
- [Referencias](#Referencias)
- [Copyright and license](#copyright-and-license)

## Introdução

O Network Mapper (NMAP) é uma ferramenta gratuita open source utilizada para mapeamento de redes e auditoria de segurança das mesmas. Capaz de detectar serviços e computadores que estão conectados em rede, bem como o gerenciamento de serviços da rede, além do monitoramento de hosts. O NMAP utiliza pacotes IP como meio de determinar quais hosts estão disponivéis na rede, quais serviços os hosts estão oeferecendo e qual sistema operacioanl eles estão rodando, qual o tipo de pacote os filtros usam e inúmeras outras caracteristicas.

## Diferenciais

O software possui alguns diferencias que podem ser citados:

- Flexivel: Suporta várias técnicas avançadas de mapeamndo de rede, utilizando filtros ip, roteadores etc;
- Portável: É possivel utilizar na maioria dos sistemas operacionais, como: Microsoft, Linux, MAC, FreeBDS, OpenBDS etc;
- Gratuito: O programa é completamente gratuito e pode ser modificado nos termos da licença;
- Poderoso: O NMAP pode mapear e análisar redes com centenas e até milhares de maquinas.

Além de outros diferenciais, como sua documentação completa e os premios recebidos como melhor produto de segurança do ano pelo Linux Journal.

## Algumas Funcionalidades

- Target Specification: Especificação de Alvo, podendo passar como parametro o endereço IP, redes, hostnames etc;
- Host Descovery: Descoberta de hosts. Pode listar alvos escaneados, buscar todos os hosts ativos, traçar um caminho para cada host e outras funções;
- Os detection: Ativa a detecção de sistemas operacionasis;
- Timing and Performance: Comandos estipular o tempo gasto e a performace dos hosts, timeouts, etc;
- Output: Saídas dos scans, mostrando as interfaces de hosts, rotas, pacotes, etc.

## Instalação

Para instalar o software no linux em distribuições baseadas no debian, como o Ubunutu 20.04 utilizado neste tutorial, basta seguir os seguintes passos:

Você pode instalar utilizando o repositório base do debian utilizando o comando:

`sudo apt-get update && sudo apt-get install nmap`

Entretando, a versão do repositório pode estar desatualizada, já que não é mantida pela equipe própria do Nmap.

A solução para instalação da versão estável mais recente é baixar o pacote RPM e converte-lo para um pacotece deb. Portanto, o passo a passo é o seguinte:

Acesse o [site de download do Nmap](https://nmap.org/download.html) e baixe a ultima versão para linux RPM.

Instale o programa Alien atráves do comando:

`sudo apt-get update && sudo apt-get install alien`

Acesse a pasta onde foi baixado o arquivo RPM e rode o seguinte comando para gerar a versão .deb:

`sudo alien nmap-version.x86_64.rpm`

Em seguida, rode o seguinte comando para instalar o Nmap:

`sudo dpkg --install nmap-version.x86_64.deb`

Após realizar esses passos o nmap já estará instalado em sua máquina.

## Utilização

O Nmap pode ser utilizado de duas maneiras, via interface gráfica e via linha de comando. A primeia opção pode ser utilizada através da ferramenta Zenmap. Porém, este tutorial utiliza linha de comando para demonstrações.

Para executar o Nmap, você deve compor uma linha de comando que irá realizar a função desejada. Todas as possibilidades de chamadas pode ser encontrada na [página guia](https://nmap.org/book/man.html#man-description) da ferramenta. A chamada base para o programa é:

`nmap [ <Scan Type> ...] [ <Options> ] { <target specification> }`

A partir dessa linha, é possivel utilizar todas as funções da ferramenta na linha de comando., como por exemplo:

## Exemplo

`nmap -v scanme.nmap.org`

Esse comando escaneia todas as portas TCP reservadas na maquina scanme.nmap.org. O -v funciona para se obter um resultado detalhado. A saída do comando é a seguinte:

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


## Referencias

Todas as instruções utilizadas neste tutorial foram desenvolvidas com base na documentação da ferramenta disponivel no site nmap.org.

## Copyright and Licença

Desenvolvido por Matheus Negrão, com base na documentação disponibilizados pela equipe do nmap em nmap.org. Sob a licença [MIT License](https://reponame/blob/master/LICENSE).