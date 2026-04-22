# Subcamada MAC

## Introdução

Faz parte da camada de enlace de dados e tem como principal função controlar o **acesso ao meio físico de transmissão**, especialmente quando esse meio é **compartilhado por várias estações**.

A camada de enlace, como um todo, garante que os dados (chamados de **quadros**) cheguem corretamente ao destino, sem erros causados pelo meio físico. Porém, quando várias máquinas tentam transmitir ao mesmo tempo em um meio compartilhado, **podem ocorrer colisões**, causando perda de dados.

Para evitar esse problema, a subcamada MAC organiza **quem pode transmitir e quando**, evitando conflitos no uso do meio.

Essa subcamada é necessária apenas em redes onde o meio físico é compartilhado e utiliza diferentes métodos de acesso, como:

* Aloha
* Slotted Aloha
* CSMA - *Carrier Sense Multiple Access*
* CSMA/CD - *Carrier Sense Multiple Access with Collision Detection*
* CSMA/CA - *Carrier Sense Multiple Access with Collision Avoidance*
* TDM - *Time Division Multiplexing*
* FDM - *Frequency Division Multiplexing*