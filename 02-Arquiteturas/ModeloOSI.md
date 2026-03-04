# Arquiteturas de Redes  

## Introdução  
Para que haja comunicação entre dispositivos, é necessário que todos sigam as mesmas regras, chamadas **protocolos**, que definem formato e sequência das mensagens.  

Inicialmente, fabricantes criavam soluções próprias, gerando incompatibilidades. A necessidade de interligar equipamentos de diferentes fabricantes levou à criação de **padrões de comunicação**.

---

# Modelo de Referência OSI da ISO (RM-OSI)

## Histórico  
Criado pela ISO – International Stantardization Organization (ou Organização
Internacional de Padronização), o **Modelo OSI (Open Systems Interconnection)** ou
Modelo de Referência – Interconexão de Sistemas Abertos, surgiu como uma proposta padronizada para interconexão de sistemas.

## Objetivo  
Definir um padrão confiável e seguro para conectar redes de qualquer porte, permitindo recuperação de falhas e proteção de dados.  
O modelo foi estruturado em **7 camadas**, cada uma com funções específicas e independentes.

## Funcionamento Geral  
- Cada camada presta serviços à camada superior.  
- A comunicação ocorre por meio de **interfaces**.  
- Cada camada adiciona informações de controle (cabeçalhos).  
- No destino, as camadas removem esses cabeçalhos sucessivamente até chegar à aplicação.
- Cada camada se comunica com a camada equivalente do outro computador por meio de protocolos específicos.

---

## As 7 Camadas do Modelo OSI

![Figura 1](/02-Arquiteturas/figura1.png)

### 1. Camada Física  
Responsável pela transmissão de bits no meio físico.  
Define sinais elétricos/óticos, conectores, duração dos bits e tipo de meio (cabo, fibra, etc.).

### 2. Camada de Enlace  
Corrige erros da camada física e organiza os dados em **quadros**.  
Pode confirmar recebimento e solicitar retransmissão.  
Inclui a subcamada **MAC (Media Access Control)** para controle de acesso ao meio.

### 3. Camada de Rede  
Responsável pelo **roteamento e endereçamento**.  
Define como os pacotes são roteados (encaminhados / repassados)
da máquina origem até a máquina destino (roteamento),
e cada máquina precisa ter um endereço único na rede (endereçamento).

Dois paradigmas principais:  
- **Comutação por circuitos:** antes das trocas de
dados é necessário estabelecer a rota da origem até o destino. (ex.: chamadas telefônicas).  
- **Comutação por pacotes:** não há a
necessidade do estabelecimento da conexão, e cada pacote é encaminhado independentemente dos
anteriores e dos seguintes até o destino. (ex.: envio de correspondências).  

O modelo OSI previa o uso do protocolo **X.25**, comutação por circuitos, orientado a conexão.

### 4. Camada de Transporte  
Garante comunicação **fim-a-fim** confiável(entre a máquina origem e a máquina destino).  
Divide dados, controla erros e permite múltiplas aplicações compartilharem a rede.  
Desse modo, para estabelecer uma comunicação com uma aplicação
específica em determinada máquina da rede, é preciso saber o endereço de rede (que identifica a
máquina dentro da rede) e o endereço de transporte (que identifica a aplicação dentro da máquina)

### 5. Camada de Sessão  
Controle das conexões entre os usuários, incluindo a
sincronização de diálogos entre dois processos e retomada de transmissões a partir do ponto em que
foi interrompida, em caso de queda da conexão.
Para isso, a camada de sessão da máquina de
origem insere marcas de sessão nos dados.

### 6. Camada de Apresentação  
Define formato e representação dos dados.  
Responsável por **criptografia** e **compressão**.

### 7. Camada de Aplicação  
Define o formato e a sequência das mensagens a serem trocados para
cada aplicação.

## Observação  
O modelo OSI é completo e formal, mas sua complexidade dificultou ampla implementação prática.
