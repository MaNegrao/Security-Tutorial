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
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Contributing](#contributing)
- [Creators](#creators)
- [Thanks](#thanks)
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

```text
folder1/
└── folder2/
    ├── folder3/
    │   ├── file1
    │   └── file2
    └── folder4/
        ├── file3
        └── file4
```

## Bugs and feature requests

Have a bug or a feature request? Please first read the [issue guidelines](https://reponame/blob/master/CONTRIBUTING.md) and search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](https://reponame/issues/new).

## Contributing



## Creators


## Thanks

Some Text

## Copyright and license

Code and documentation copyright 2011-2018 the authors. Code released under the [MIT License](https://reponame/blob/master/LICENSE).

Enjoy :metal:
