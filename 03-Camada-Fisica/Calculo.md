### Formulas para calcular as Relações fundamentais de modulação digital

## 1. Taxa de bits(Bit Rate)
É a quantidade de bits transmitidos por segundo.

```
Rb​ = Rs ​⋅ n
```

### Onde:
* **Rb** = taxa de bits (bits/s)
* **Rs** = taxa de sinais (sinais/s)
* **n**  = número de bits por sinal

## 2. Bits por sinal
É quantos bits cada sinal carrega.

```
n = log<sub>2</sub>(M)
```

### Onde:
* **n** = bits por símbolo
* **M** = número de níveis do sinal

## 3. Número de niveis por sinal
Quantidade de estados diferentes que o sinal pode assumir.

```
M = 2^n
```
### Onde:
* **M** = niveis do sinal
* **n** = bits por sinal

## 4. Taxa de sinal(Baud Rate)
É quantos sinais são transmitidos por segundo.

```
Rs​ = $\frac{Rb}{n}$
```

## Onde:
* **Rs** = taxa de sinal
* **Rb** = taxa de bits
* **n** = bits por sinal


## Exemplo
Se um sistema tem:
* M = 8 níveis

Então:
```
n = log<sub>2</sub>(8) = 3 bits por segundo  ​
```

Se:
* Rs = 1000 baud

Então:
* Rb = 1000 ⋅ 3 = 3000 bits/s