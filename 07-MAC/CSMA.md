# Subcamada MAC

## CSMA (Carrier Sense Multiple Access)

Quando uma estação deseja enviar dados, ela escuta o meio físico.

* Se o meio estiver **livre**, ela **transmite**.
* Se estiver **ocupado**, ela **adiará** a transmissão.

Existem três variações principais:

* **CSMA persistente (1-persistente):** a estação continua ouvindo o meio até que fique livre e **transmite imediatamente.**
* **CSMA não-persistente (0-persistente):** ao encontrar o meio ocupado, a estação espera um **tempo aleatório** antes de tentar novamente.
* **CSMA p-persistente:** usado em sistemas com intervalos de tempo (slots), **transmite com uma probabilidade p** quando o meio está livre, ou espera com probabilidade (1-p).

Comparado aos métodos ALOHA, o CSMA **diminui significativamente o número de colisões**, pois evita transmissões simultâneas desnecessárias. Ainda assim, colisões podem ocorrer quando duas estações começam a transmitir quase ao mesmo tempo, devido ao tempo de propagação do sinal na rede.

---

## CSMA/CD (Carrier Sense Multilpe Access with Collision Detection)

A diferença principal é que, durante a transmissão, a **estação continua monitorando o meio**. Se perceber alguma interferência (indicando uma colisão), ela:

* Interrompe imediatamente a transmissão
* Libera o meio para outras estações
* Tenta novamente depois

Isso **reduz o desperdício de tempo**, já que não é necessário esperar o envio completo de um quadro corrompido para identificar a colisão.

Apesar disso, **colisões ainda podem acontecer**, principalmente por causa do **tempo de propagação do sinal**(quando duas estações começam a transmitir quase ao mesmo tempo). Porém, como são detectadas rapidamente, o impacto é menor.

![CSMA/CD](/07-MAC/img/figura3.png)

O CSMA/CD pode operar nas variações persistente, não persistente ou p-persistente, e foi amplamente utilizado em **redes como Ethernet**, oferecendo desempenho superior ao CSMA, ALOHA e Slotted ALOHA.

---

## CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)

Foi desenvolvido para** redes sem fio**, como o Wi-Fi, onde não é possível detectar colisões durante a transmissão, diferentemente do CSMA/CD.

Em redes wireless, o sinal transmitido por uma estação é muito mais forte do que os sinais recebidos de outras, o que **impede a detecção de colisões em tempo real**. Por isso, o CSMA/CA foca em evitar colisões antes que elas aconteçam.

Seu funcionamento é semelhante ao CSMA no início:

* A estação escuta o meio
* Se estiver livre, inicia o processo de transmissão

Porém, antes de enviar os dados, utiliza dois quadros de controle:

* **RTS (Request To Send):** solicita permissão para transmitir
* **CTS (Clear To Send):** resposta autorizando a transmissão

![RTS/CTS](/07-MAC/img/figura4.png)

Esses quadros** avisam todas as estações** ao redor para **ficarem em silêncio por um tempo determinado** (NAV), reservando o meio para a comunicação.

Isso reduz colisões nos quadros principais de dados, **embora ainda possam ocorrer colisões nos quadros de controle (RTS/CTS)**, que são menores e causam menos impacto.

![NAV](/07-MAC/img/figura5.png)

Além disso, o CSMA/CA lida com o problema do alcance variável nas redes sem fio, onde nem todas as estações conseguem “ouvir” umas às outras.
