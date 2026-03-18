# A Camada Fisica

## Introdução
A **camada física** é responsável por transmitir bits entre máquinas por meio de **sinais físicos** (elétricos, ópticos ou eletromagnéticos). Ela define tanto o **meio de transmissão** (cabos, fibra, etc.) quanto a forma de **codificação** dos bits em sinais.
O projeto da camada física precisa espeficiar:

* **Atenuação:** perda de intensidade de sinal, ilimitando a distância de transmissão.

---

## Sinais

### 1. Analogicos
Possuem uma **variação contínua** ao longo do tempo, e **qualquer valor**
dentro de certos limites é **considerado válido.**
Por exemplo, se o meio físico suporta sinais elétricos analógicos 
entre -12V e +12V, a quantidade de valores possíveis nessa faixa é
infinita, pois qualquer valor no intervalo [-12, +12] é válido.

![Sinal Analogico](/03-Camada-Fisica/img/figura1.png)

### 2. Digitais
Podem assumir apenas uma **gama discreta** de valores convencionados,
permanecendo em um determinado patamar durante um tempo e mudando
rapidamente para outro patamar, **estabilizando novamente.**
Qualquer valor diferente será **arredondado para o valor mais próximo.**

![Sinal Digital](/03-Camada-Fisica/img/figura2.png)

---

## Modulação

Como os meios físicos transportam melhor sinais analógicos,
os bits digitais são convertidos em analogicos
A modulação consiste em inserir uma informação alterando uma ou mais
características de uma onda conhecida por ambas as partes, **denominada portadora.**

### 1. AM (Amplitude Modulation)
altera-se a **amplitude (intensidade)**
da onda portadora de acordo com a informação que se quer transmitir.

![AM](/03-Camada-Fisica/img/figura3.png)

### 2. FM (Frequency Modulation)
altera-se a **frequência (número de oscilações por segundo)**
da onda portadora, de acordo com a informação que se quer transmitir.
A frequência de uma onda (medida em Hertz – Hz), indica a quantidade de oscilações
da onda por segundo **(1Hz = 1 oscilação completa da onda por segundo).**

![FM](/03-Camada-Fisica/img/figura4.png)

### 3. PM (Phase Modulation)
altera-se a **fase (a posição que a onda se encontra, dentro do seu ciclo)**
da onda portadora, de acordo com a informação que se quer transmitir.

![PM](/03-Camada-Fisica/img/figura5.png)

---

### Comparação

![Comparacao](//03-Camada-Fisica/img/figura6.png)

Neste caso, para a modulação por amplitude há duas amplitudes diferentes, uma para o bit 0 e outra
para o bit 1, na modulação por frequência há duas frequências diferentes, uma para o bit 0 e
outra para o bit 1, e na modulação por fase, há o desvio de fase em 180º no início de cada bit
1. Nos bits 0 não há mudança de fase.

---

## Modem
Aparelho responsavel por fazer o processo inverso da modularização
extraindo as informações presentes em uma onda portadora


* Bits são convertidos em sinais → enviados pelo meio físico → recebidos → decodificados.

---

## Interferencia eletromagnetica
Eventuais alterações no sinal original, geradas por eventuais correntes eletricas induzidas

**Harmonicos:** Outras ondas com múltiplos da frequência fundamental da onda principal
que resulta na soma das ondas.

![Interferencia](/03-Camada-Fisica/img/figura7.png)

Devido a essa interferência, uma informação que representa o bit 1, 
pode ser distorcido no caminho até o destino, e ser interpretado
como um sinal que representa o bit 0, **causando um erro.**
Os protocolos das **camadas superiores (notadamente o enlace)** insere informações
adicionais para conferir se houve algum erro em um ou mais bits, e em caso afirmativo
solicita ao transmissor para enviar novamente o quadro.

* Quando mais erros, mais retrasmissão, menos desempenho

### Limite da capacidade e transmissão
Um sinal pode representar mais de 1 bit, dependendo do número de níveis possíveis.
Esta é uma forma de aumentar a capacidade de transmissão de um meio de
comunição.

8 níveis → 3 bits por sinal
16 níveis → 4 bits por sinal
32 níveis → 5 bits por sinal

Por exemplo, se um canal de comunicação suporta uma taxa de sinalização de
1.000 sinais enviados por segundo, e suporta a identificação com clareza de 32 níveis
diferentes de sinal, podemos ter 32 sinais diferentes, o que significa que precisaremos de 5
bits para representar cada sinal, pois 2⁵ = 32. Logo, esse canal pode tranportar 5.000 bits por
segundo (1.000 sinais por segundo, cada sinal carregando 5 bits).

* Mais níveis = maior taxa de transmissão, mas maior sensibilidade a ruídos.

* Mais níveis → mais velocidade

* Menos níveis → mais confiabilidade

