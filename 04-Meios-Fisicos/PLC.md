# Meios Físicos de Transmissão I

Os meios guiados podem ser classificados em meios magnéticos (cabos metálicos) e ópticos
(fibra óptica).

---

## Linha de Energia Eletrica (PLC)
Devido ao alto custo de instalação de novos cabos metálicos para transmissão de dados, 
surgiu a tecnologia PLC (Power Line Communications), que utiliza 
a **rede elétrica existente** para transmitir dados e acesso à Internet.

Essa tecnologia possui **duas aplicações principais**:

### PLC Outdoor (Internet pela rede elétrica)

A primeira aplicação é fornecer acesso à **Internet pela rede pública de energia elétrica**,
funcionando como uma **rede metropolitana (MAN)**.

![PLC para fornecimento de Internet.](/04-Meios-Fisicos/img/figura10.png)

Nesse caso:
Os dados trafegam pela rede elétrica externa
A operadora de energia precisa instalar equipamentos especiais
Esses equipamentos desviam os dados dos **transformadores de alta tensão**
Isso é necessário porque transformadores não deixam o sinal de dados passar

No Paraná, a **COPEL** realizou testes com essa tecnologia em algumas cidades, mas:

- O serviço não foi expandido comercialmente
- Foi descontinuado
- A **solução com fibra óptica** foi priorizada

### PLC Indoor (Rede local pela rede elétrica)
A segunda aplicação é criar uma **rede local (LAN**) usando a fiação elétrica interna da casa ou prédio.
Esse método é útil quando:
* Não é possível passar novos cabos
* Prédios históricos
* Tubulações entupidas
* Móveis fixos dificultando instalação

![Rede local usando PLC e exemplo de equipamento.](/04-Meios-Fisicos/img/figura11.png)

Nesse sistema:
- A rede elétrica funciona em **topologia barramento**
- O sinal se espalha por toda a fiação elétrica
- Todos os pontos conectados compartilham o meio
- Limitações da rede PLC

Alguns fatores podem afetar o funcionamento:

**Fases diferentes**
* Casas podem ter duas ou três fases
* O sinal só se propaga na mesma fase
* Tomadas em outra fase não recebem sinal

**Fiação antiga**
- Oxidação causa interferência
- Reduz qualidade da comunicação

**Disjuntores**
* Ramais diferentes podem bloquear o sinal
* Pode ser necessário instalar acoplador no quadro elétrico

### Funcionamento do PLC

O PLC funciona transmitindo dados em **frequências diferentes da energia** elétrica:
* Energia elétrica: 50 a 60 Hz
* Dados PLC: 1 a 30 MHz

Como as frequências são diferentes, os dois sinais podem **conviver no mesmo fio** sem interferência.
Isso permite:
- Internet e energia no mesmo cabo
- Funcionamento simultâneo
- Comunicação contínua

![Dados em alta frequência transmitidos sobre a rede elétrica.](/04-Meios-Fisicos/img/figura12.png)