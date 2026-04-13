# Meios Físicos de Transmissão II

Os meios físicos não guiados são aqueles em que o sinal do emissor não é conduzido por
algum tipo de cabo, sendo propagado pelo ar ou até mesmo pelo vácuo. São as comunicações sem
fio.
Esse tipo de comunicação complementa as redes de transmissão com fio, especialmente
onde é necessário mobilidade, ou onde é caro, difícil ou mesmo impossível passar cabos.

---

## Espectro Eletromagnético

### Origem
Ondas eletromagnéticas são **geradas pelo movimento de elétrons**.
Elas podem se propagar até no vácuo (não precisam de meio material).
Foram:
Previstas por James Clerk Maxwell em 1865
Confirmadas experimentalmente por **Heinrich Hertz em 1887**

### Relação Fundamental

* **Frequência (f):** número de oscilações por segundo **(medida em Hz)**.

* **Comprimento de onda (λ):** distância entre **dois pontos equivalentes consecutivos** (como picos).

Relação entre os dois:

λ ⋅ f = c

Onde:
c = velocidade da luz (~3 × 10⁸ m/s no vácuo)
No cobre ou na fibra, a velocidade cai para cerca de 2/3 desse valor e se torna ligeiramente dependente da
frequência. A velocidade da luz é o limite máximo que se pode alcançar. Nenhum objeto ou sinal
pode se mover com maior rapidez do que ela.

* Consequência:
    - Frequência **Maior:** comprimento de onda **menor**
    - Comprimento de onda **Maior:** frequência **menor**

### Espectro

O espectro eletromagnético inclui várias faixas, como **rádio, micro-ondas, infravermelho e luz visível**, que podem ser usadas para transmitir informações por meio da modulação das ondas. Faixas de frequência mais altas, como **ultravioleta, raios X e gama**, têm maior potencial, mas são pouco utilizadas por serem difíceis de manipular, perigosas e com baixa capacidade de atravessar obstáculos.

As **bandas de frequência** são padronizadas pela ITU e classificadas conforme o comprimento de onda (como LF, MF e HF). Com o avanço tecnológico, surgiram novas classificações para frequências mais altas.

O pesquisador Shannon demonstrou que a quantidade de informação transmitida depende da potência do sinal e da largura de banda. Por isso, tecnologias como fibras ópticas são muito valorizadas, pois oferecem larguras de banda extremamente altas, permitindo taxas de transmissão muito superiores às das micro-ondas, podendo chegar a centenas de Tbps.

![espectro eletromagnetico](/05-Meios-Fisicos-II/img/figura1.png)

A escala do espectro eletromagnético é **logarítmica**, ou seja, cada faixa aumenta em **potências de 10**. Isso significa que, embora algumas bandas pareçam menores no gráfico, sua largura real pode ser muito maior.

Por exemplo, a faixa de satélites possui uma largura de banda muito superior à de pares trançados. Enquanto os pares trançados têm quase 100 MHz de largura, a faixa de satélites pode chegar a cerca de 9 GHz, sendo aproximadamente 90 vezes maior.