# Introdução ao Kathará

O Kathará é um ambiente para emulação de redes de computadores através da criação de contêineres Docker em uma máquina hospedeira.

Cada contêiner pode ser configurado como um dispositivo de rede específico e pode desempenhar diferentes papeis, como host, roteador, switch etc.

## Dispositivos de rede
* Cada dispositivo de rede emulado possui as seguintes características:
    - console
    - memória
    - sistema de arquivos
    - interfaces de rede

Através das interfaces de rede os dispositivos são conectados a um domínio de colisão virtual e podem se comunicar com outros dispositivos.

## Comandos

O Kathará apresenta três tipos de comandos, utilizados em um terminal:

* **v-commands:** permitem criar e configurar um dispositivo via terminal.
* **l-commands:** permite criar um ambiente com vários dispositivos conectados em rede através de um script.
***global-commands:** comandos de gerenciamento global.

A relação completa dos comandos pode ser encontrada no manual do Kathará em: `man kathara`

## Compartilhamento de arquivos

O Kathará permite o compartilhamento de arquivos entre dispositivos e o hospedeiro.
	
Há duas maneiras de compartilhar arquivos entre dispositivos e o hospedeiro:

- O diretório /shared em um dispositivo aponta para o diretório /shared de todos os dispositivos do laboratório (habilitado por default).
- O diretório /hosthome em um dispositivo aponta para o diretório /home no hospedeiro (desabilitado por default).

Para modificar os compartilhamentos utilizar o comando: `kathara settings`

## Teste

Para verificar se o Kathara está funcionando adequadamente, execute o comando de teste do Kathara: `kathara check`

Habilite a montagem da pasta /hosthome na inicialização das máquinas, para permitir gravar arquivos no hospedeiro (kathara settings). 

Escolha a opção Automatically mount /hosthome on startup. Se estiver com status corrente No, escolha opção 1 – Yes para habilitar. 

Em seguida, retorne ao menu principal e encerre o comando.