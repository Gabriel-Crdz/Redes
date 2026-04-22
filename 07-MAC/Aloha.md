# Subcamada MAC

## Aloha
**Cada estação transmite dados assim que tiver algo a enviar, sem verificar se o meio está livre**. Se ocorrer uma colisão (duas transmissões ao mesmo tempo), **os dados são perdidos**. Quando isso acontece, a estação aguarda um **tempo aleatório antes de tentar novamente**, evitando novas colisões simultâneas.

Caso ocorram colisões repetidas, o tempo de espera aumenta progressivamente por meio do **recuo exponencial binário**, dobrando o tempo a cada nova tentativa até um limite.

Apesar de ser simples, o ALOHA só funciona bem **quando há baixo uso do canal**. Em situações com muitas transmissões, as colisões aumentam, gerando mais retransmissões e reduzindo significativamente a eficiência da rede.

![aloha](/07-MAC/img/figura1.png)

---

## Slotted Aloha

A principal diferença é que o tempo passa a ser **dividido em intervalos fixos (slots)**, cada um com duração suficiente para transmitir um quadro completo. As estações só podem transmitir no início desses intervalos, o que evita colisões parciais (como o fim de um quadro colidir com o início de outro). Assim, quando ocorre uma colisão, os quadros envolvidos **são perdidos por completo**.

Para que isso funcione, é necessário **sincronismo entre as estações**, geralmente coordenado por um sistema central.

Assim como no ALOHA tradicional:

* Não há reserva prévia de tempo para transmissão
* A estação transmite no próximo intervalo disponível
* Em caso de colisão, **espera um tempo aleatório** antes de tentar novamente
* Utiliza o **recuo exponencial binário** em colisões sucessivas

![slotted aloha](/07-MAC/img/figura2.png)

Slotted ALOHA melhora a eficiência ao organizar o tempo de transmissão, reduzindo colisões, mas ainda pode apresentar perdas quando várias estações transmitem no mesmo intervalo.
