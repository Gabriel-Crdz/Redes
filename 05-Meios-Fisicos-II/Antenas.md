# Antenas

O sinal eletromagnético é gerado por um **transmissor e irradiado por uma antena**, que pode dispersar a energia em diferentes direções conforme seu tipo. Embora as ondas tendam a se espalhar igualmente, isso nem sempre é **ideal para comunicação entre pontos distantes,** sendo necessário o uso de antenas direcionais.

Isso pode ser muito útil por exemplo para emissoras de **rádio difusão (AM e FM) e TV,** 
mas não é a melhor opção para estabelecer um enlace de dados entre dois pontos distantes.

Um fator importante é o **ganho da antena (medido em dBi)**, que indica sua capacidade de concentrar a energia do sinal. A cada aumento de 3 dBi, a intensidade do sinal dobra. No entanto, **antenas passivas** não amplificam o sinal, apenas direcionam melhor a energia.

---

## Omnidirecionais

As antenas omnidirecionais distribuem o sinal de **forma uniforme em todas as direções** no plano horizontal, sendo ideais para cobrir áreas ao redor da antena. São comuns em ambientes internos, como roteadores Wi-Fi, e também em aplicações externas, como **transmissões de rádio e TV.**

![uso interno](/05-Meios-Fisicos-II/img/figura3.png)

Seu padrão de irradiação forma um **círculo de 360° na horizontal** e um formato **semelhante a uma “maçã”** na vertical. Antenas com maior ganho **concentram mais o sinal no plano horizontal**, aumentando o alcance nessa direção, mas reduzindo a cobertura vertical.

![diagrama 2.2 dBi](/05-Meios-Fisicos-II/img/figura4.png)

![uso externo 15 dBi](/05-Meios-Fisicos-II/img/figura5.png)
![diagrama 15 dBi](/05-Meios-Fisicos-II/img/figura6.png)

![diagramas comparação](/05-Meios-Fisicos-II/img/figura7.png)

---

## Parabólicas

Concentram o sinal em **uma única direção**, utilizando um formato em parábola com o transmissor no foco, semelhante ao funcionamento de um farol. Isso permite maior alcance ao direcionar a energia em um feixe mais estreito.

![antena](/05-Meios-Fisicos-II/img/figura8.png)

São usadas em diversas aplicações, como recepção de TV por satélite e transmissão de dados (ex.: Wi-Fi). Seu padrão de irradiação é **altamente direcionado**, com foco para frente, sendo ideais para conexões de **longa distância**, geralmente **ponto a ponto**, embora também possam atender múltiplos dispositivos alinhados no mesmo feixe.

![diagrama](/05-Meios-Fisicos-II/img/figura9.png)

---

## Setoriais

Possuem um padrão de cobertura intermediário **entre as omnidirecionais e as parabólicas**, direcionando o sinal para um setor específico, **com ângulos comuns de 60°, 90° ou 120°.**

São amplamente usadas em torres de** telefonia celular** e provedores de internet sem fio. Para cobrir 360°, utilizam-se várias antenas combinadas, podendo haver sobreposição entre elas. Seu padrão de irradiação geralmente é mais aberto na horizontal e inclinado para baixo na vertical, alcançando usuários próximos.

![exemplo, com diagrama](/05-Meios-Fisicos-II/img/figura10.png)

Atualmente, é comum que essas antenas já venham integradas a **equipamentos como Access Points Wi-Fi** para uso externo.
