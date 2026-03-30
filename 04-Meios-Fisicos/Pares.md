# Meios Físicos de Transmissão I

Os meios guiados podem ser classificados em meios magnéticos (cabos metálicos) e ópticos
(fibra óptica).

---

## Pares Trançados

É um dos meios de transmissão **mais antigos e ainda amplamente utilizados**. Ele é formado por dois fios de cobre encapados, com cerca de 1 mm de espessura, trançados em **forma helicoidal, semelhante ao DNA**. Esse trançamento reduz interferências eletromagnéticas, pois os ruídos que afetam um fio tendem a afetar o outro igualmente, mantendo a **diferença de potencial (ddp)** praticamente inalterada.
Esse tipo de cabo possui **boa imunidade ao ruído externo**, já que o sinal é transmitido pela diferença de tensão entre os dois fios. Assim, interferências externas afetam ambos de forma semelhante e não prejudicam a comunicação.
A aplicação mais comum é no **sistema telefônico**, conectando telefones às centrais. Também é utilizado em **acesso à internet ADSL.** Esses cabos podem percorrer **vários quilômetros sem amplificação**, mas em distâncias maiores o sinal sofre atenuação, sendo necessário o uso de repetidores.
Quando muitos pares são agrupados, eles recebem uma **capa protetora**, evitando interferências entre os próprios cabos. É comum ver esses cabos em postes com **vários centímetros de diâmetro.**
Os pares trançados podem transmitir **sinais analógicos ou digitais**, e a largura de banda depende da espessura do fio e da distância. Mesmo assim, podem alcançar **diversos megabits por segundo**, embora estejam sendo gradualmente **substituídos por fibras ópticas**.

### Tipos de cabeamento

Um dos mais comuns é o **Categoria 5 (Cat 5) e sua versão Cat 5e**.
Um cabo Cat 5 é composto por **dois fios isolados e trançados**, 
e normalmente quatro pares são agrupados dentro de uma capa plástica.

![Cabo UTP Categoria 5](/04-Meios-Fisicos/img/figura1.png)

Diferentes redes LAN utilizam esses pares de formas distintas:

* Ethernet 100 Mbps → **usa 2 pares** (um para cada direção)
* Ethernet 1 Gbps → **usa 4 pares** simultaneamente

O Cat 5 substituiu o Categoria 3, oferecendo:

* Mais voltas por metro
* Menos interferência
* Melhor qualidade de sinal
* Maior velocidade

O Cat 5e é uma melhoria do Cat 5, com trançamento modificado para suportar até 1 Gbps.
Para velocidades maiores são **usados Cat 6 e Cat 7.**

O Cat 6 possui um separador plástico em forma de X isolando os pares.

![Cabo UTP Categoria 6](/04-Meios-Fisicos/img/figura2.png)

#### UTP (Unshielded Twisted Pair)

Os cabos mais comuns em redes locais são os **UTP (par trançado não blindado)**.
Quando o cabo precisa passar junto com cabos de energia elétrica, usa-se o FTP, 
que possui blindagem metálica (tipo papel alumínio) para reduzir interferência eletromagnética.

Os mais **usados comercialmente** são:

* UTP Cat 5e
* UTP Cat 6
* FTP (Foiled Twisted Pair)

![Cabo FTP Cat5e](/04-Meios-Fisicos/img/figura3.png)

#### Cabos para uso externo

Quando o cabo será **usado em ambiente externo**, ele recebe uma proteção plástica adicional, 
geralmente preta, para resistir às intempéries.

![Cabo com proteção externa](/04-Meios-Fisicos/img/figura4.png)

Os cabos Cat5e e Cat 6a permitem a conexão a até 100m.

---

### Confecção

Os cabos padrões de rede local utilizam em cada ponta um **conector padrão RJ45**, que
é um conector cescartável com estrutura plástica e contatos metálicos, **para 8 fios (4 pares)**

![Conector RJ45](/04-Meios-Fisicos/img/figura5.png)

Os pinos do conector são numerados de **1 a 8**. 
Observando o conector de frente, com os contatos metálicos voltados para cima, 
o pino **1 fica à esquerda** e o pino **8 à direita**.
Existem dois tipos principais de cabos usados em redes Ethernet:
* **Cabo Direto:** conecta uma placa de computador a um hub/switch, *conexão é pino a pino*
* **Cabo cruzado (Crossover):** conectar dois computadores diretamente, 
conexão **invertendo os pares laranja e verde**

![Pinagem direta](/04-Meios-Fisicos/img/figura6.png)
![Pinagem cruzada](/04-Meios-Fisicos/img/figura7.png)

#### Pares de cores do cabo Cat 5e e Cat 6
Os cabos possuem 4 pares trançados:

- Branco/Verde e Verde
- Branco/Laranja e Laranja
- Branco/Azul e Azul
- Branco/Marrom e Marrom

Para montar o cabo:

1. Remover cerca de 8 a 10 cm da capa externa
2. Identificar os pares
3. Destrançar as pontas
4. Organizar na ordem correta
5. Cortar as pontas niveladas
6. Inserir no conector RJ45

### ADSL
Outra aplicação dos cabos de pares trançados é a **tecnologia ADSL**, 
que utiliza o **mesmo par de fios da linha telefônica** para transmitir voz e dados simultaneamente.

Nesse sistema são usados dois equipamentos principais:

* **Modem ADSL** lado do cliente
* **DSLAN (Multiplexador ADSL):** lado da operadora

Assim, cada assinante possui **um meio físico exclusivo**, ou seja, 
**não compartilha o cabo com os vizinhos**, evitando competição por banda. 
A conexão física **funciona em topologia estrela**, onde todos os 
assinantes são ligados diretamente ao equipamento da operadora no bairro.

![Esquema de conexão ADSL](/04-Meios-Fisicos/img/figura8.png)

O funcionamento ocorre da seguinte forma:

- O mesmo cabo telefônico (PSTN) leva voz e dados
- O sinal de dados utiliza frequências mais altas
- O sinal de voz utiliza frequências mais baixas
- Ambos trafegam simultaneamente no mesmo cabo

* O cabo é conectado à rede telefônica (PSTN)
* Também é conectado ao Multiplexador ADSL (DSLAN)
* Na casa do usuário é instalado um modem ADSL

Os **splitters** são utilizados como filtros de frequência, separando:

* **Canal de voz:** telefone
* **Canal de dados:** modem ADSL