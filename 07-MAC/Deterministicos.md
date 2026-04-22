# Subcamada MAC

* **Não determinísticos:** podem ter colisões e tempo de espera imprevisível
    - ALOHA
    - Slotted ALOHA
    - CSMA

* **Determinísticos:** não têm colisões e possuem tempo de transmissão previsível
    - FDM
    - TDM
    
---

## FDM (Frequency Division Multiplexing)

É uma técnica que permite que vários usuários compartilhem o **mesmo meio físico ao mesmo tempo**, dividindo-o em **diferentes faixas de frequência**.

Cada usuário recebe um **canal exclusivo**, operando em uma frequência específica. Como sinais em frequências diferentes não interferem entre si, é possível realizar transmissões simultâneas de forma independente.

![FDM](/07-MAC/img/figura6.png)

A capacidade total do meio é **dividida entre os canais**, com pequenas faixas de separação (margens de segurança) para evitar interferências.

Uma característica importante é que a **largura de banda de cada canal é fixa**. Isso significa que, se um usuário não estiver transmitindo, **seu canal fica ocioso** e não pode ser utilizado por outros.

Exemplos comuns de uso do FDM incluem:
* Rádio AM e FM
* Transmissão de TV

---

## TDM (Time Division Multiplexing)

É uma técnica em que vários usuários compartilham o mesmo meio físico **dividindo o tempo em intervalos (slots)**. Cada usuário transmite **em seu próprio intervalo de tempo**, de forma alternada, utilizando toda a capacidade do canal naquele momento.

A alocação desses intervalos pode ser:

* **Estática:** cada usuário tem um tempo fixo reservado; se não usar, o tempo fica ocioso
* **Dinâmica (STDM):** os intervalos são distribuídos conforme a demanda, permitindo que estações com mais dados utilizem mais tempo

![TDM](/07-MAC/img/figura7.png)

Diferente do FDM, que divide por frequência, o TDM organiza o acesso ao longo do tempo.

Um exemplo de uso do **TDM é o Bluetooth**.

---

## Combinado TDM e FDM

TDM pode ser combinado com o FDM para criar sistemas mais eficientes e flexíveis. Nessas combinações:

* O meio é dividido em frequências (FDM)
* Cada frequência é subdividida em intervalos de tempo (TDM)

Essa abordagem é usada em tecnologias como:
* Comunicação via satélite
* Telefonia celular (como o padrão GSM)
* WiMAX

Nesses três exemplos, há mais de um canal FDM, e cada canal FDM ainda é
multiplexado usando TDM, com alocação dinâmica de intervalos de transmissão

![FDM-TDM](/07-MAC/img/figura8.png)