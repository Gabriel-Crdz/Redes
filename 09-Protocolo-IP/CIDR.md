# Protocolo IP

## CIDR (Classless Inter-Domain Routing)

O CIDR criado em 1993, surgiu para tornar o uso dos endereços IPv4 mais eficiente, eliminando a limitação rígida das classes A, B e C.

No CIDR, o tamanho da rede é definido pela quantidade de bits 1 na máscara de rede (Netmask). As máscaras tradicionais continuam existindo:

/8 → 255.0.0.0 (Classe A)
/16 → 255.255.0.0 (Classe B)
/24 → 255.255.255.0 (Classe C)

Porém, agora é possível criar redes de tamanhos variados conforme a necessidade.

Exemplo:
Uma empresa que precise de cerca de 1000 IPs não precisa receber uma rede Classe B inteira com mais de 65 mil endereços. Pode receber uma rede com 1024 endereços usando:

máscara /22
equivalente a 255.255.252.0

Nesse caso:

* 22 bits identificam a rede;
* 10 bits identificam os hosts.

O CIDR reduz o desperdício de endereços IP e permite subdividir redes maiores em sub-redes menores, algo muito utilizado por operadoras e provedores de Internet.

### Subnetmask classe C
Uma rede Classe C utiliza:

* 24 bits para identificar a rede;
* 8 bits para identificar os hosts.

Com subnetting (subdivisão de rede), parte dos bits de host pode ser usada para criar sub-redes menores.

As fórmulas são:

* Quantidade de sub-redes: **2^r**
* Quantidade de hosts por sub-rede: 2^(8−r) − 2

Onde:
**r** = quantidade de bits “emprestados” para criar sub-redes;
“−2” existe porque:
- o primeiro endereço é o endereço da rede;
- o último é o endereço de broadcast.

Exemplo:
Ao usar 1 bit adicional para rede em uma Classe C:

máscara passa de /24 para /25;
máscara decimal: 255.255.255.128.

| 255 | 255 | 255 |128 |
|---|---|---|---|
| 11111111 | 11111111 | 11111111 | 10000000 |

Isso divide a rede em duas sub-redes com 126 hosts válidos em cada sub-rede.

Cada sub-rede possui:
* 128 endereços totais;
* 2 reservados (rede e broadcast);
* 126 utilizáveis para dispositivos.

Vamos relembrar os valores decimais de cada posição binária de um byte:

| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
|---|---|---|---|---|---|---|---|
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |

O valor em decimal do endereço IP é obtido somando os correspondentes
valores decimais das casas que têm o bit 1.

Exemplo: 192 = 11000000 = 128 + 64

Seguem outros exemplos, com 26, 27, 28, 29 e 30 bits de máscara de rede. 
De agora em diante, vou representar em binário somente o último byte
do Nemask. Considere que os primeiros 24 bits (3 bytes) são 1.

#### Máscara /26 = 255.255.255.192 
(11000000) = 128 + 64

No último byte temos 2 bits 1 e 6 bits 0

Essa máscara pode representar 4 sub-redes (2)2 com 62 hosts cada (2)6 – 2
sendo:

**Sub-redes com máscara 26 bits**
| Endereço da rede | Estações (hosts) | Endereço de Broadcast |
|----|----|----|
| x.x.x.0 | x.x.x.1 a x.x.x.62 | x.x.x.63 |
| x.x.x.64 | x.x.x.65 a x.x.x.126 | x.x.x.127 |
| x.x.x.128 | x.x.x.129 a x.x.x.190 | x.x.x.191 |
| x.x.x.192 | x.x.x.193 a x.x.x.254 | x.x.x.255 |


#### Máscara /27 = 255.255.255.224 
(11100000) = 128 + 64 + 32

No último byte temos 3 bits 1 e 5 bits 0.

Essa máscara pode representar (2)3 = 8 sub-redes, cada uma com (2)5 – 2 = 30
hosts, sendo:

**Sub-redes com máscara 27 bits**
| Endereço da rede | Estações (hosts) | Endereço de Broadcast |
|----|----|----|
| x.x.x.0 | x.x.x.1 a x.x.x.30 | x.x.x.31 |
| x.x.x.32 | x.x.x.33 a x.x.x.62 | x.x.x.63 |
| x.x.x.64 | x.x.x.65 a x.x.x.94 | x.x.x.95 |
| x.x.x.96 | x.x.x.97 a x.x.x.126 | x.x.x.127 |
| x.x.x.128 | x.x.x.129 a x.x.x.158 | x.x.x.159 |
| x.x.x.160 | x.x.x.161 a x.x.x.190 | x.x.x.191 |
| x.x.x.192 | x.x.x.193 a x.x.x.222 | x.x.x.223 |
| x.x.x.224 | x.x.x.225 a x.x.x.254 | x.x.x.255 |


#### Máscara /28 = 255.255.255.240 
(11110000) = 128 + 64 + 32 + 16

No último byte temos 4 bits 1 e 4 bits 0.

Essa máscara pode representar (2)4 = 16 sub-redes, cada uma com (2)4 – 2 =
14 hosts, sendo:

**Sub-redes com máscara 28 bits**
| Endereço da rede | Estações (hosts) | Endereço de Broadcast |
|----|----|----|
| x.x.x.0 | x.x.x.1 a x.x.x.14 | x.x.x.15 |
| x.x.x.16 | x.x.x.17 a x.x.x.30 | x.x.x.31 |
| x.x.x.32 | x.x.x.33 a x.x.x.46 | x.x.x.47 |
| x.x.x.48 | x.x.x.47 a x.x.x.62 |x.x.x.63 |
| x.x.x.64 |x.x.x.65 a x.x.x.78 | x.x.x.79 | 
| x.x.x.80 | x.x.x.81 a x.x.x.94 | x.x.x.95 |
| x.x.x.96 | x.x.x.97 a x.x.x.110 | x.x.x.111 |
| x.x.x.112 | x.x.x.113 a x.x.x.126 | x.x.x.127 |
| x.x.x.128 | x.x.x.129 a x.x.x.142 | x.x.x.143 | 
| x.x.x.144 | x.x.x.145 a x.x.x.158 | x.x.x.159 |
| x.x.x.160 | x.x.x.161 a x.x.x.174 | x.x.x.175 |
| x.x.x.176 | x.x.x.177 a x.x.x.190 | x.x.x.191 |
| x.x.x.192 | x.x.x.193 a x.x.x.206 | x.x.x.207 |
| x.x.x.208 | x.x.x.209 a x.x.x.222 | x.x.x.223 |
| x.x.x.224 | x.x.x.225 a x.x.x.238 | x.x.x.239 |
| x.x.x.240 | x.x.x.241 a x.x.x.254 | x.x.x.255 |

**Observe que a formação dessas tabelas tem algumas regras:**
1. A coluna do endereço de rede é sempre par e do Broadcast é sempre ímpar.
2. O endereço de rede vai aumentando exatamente o número equivalente a 2^h,
onde h=(8-r), é o número de bits reservado para host.
3. O broadcast é o número anterior ao próximo endereço de rede.
4. O último endereço de rede é sempre o final do netmask.
5. O primeiro endereço de rede é o 0 e o último broadcast é o 255.
6. Em cada sub-rede, os endereços de hosts são os que estão entre o endereço
de rede e o broadcast


#### Máscara /29 = 255.255.255.248 
(11111000) = 128 + 64 + 32 + 16 + 8

No último byte temos 5 bits 1 e 3 bits 0.

Essa máscara pode representar (2)^5 = 32 sub-redes, cada uma com (2)^3 – 2 = 6
hosts.

Seguindo as regras acima, r=5, h=8-5=3, as redes serão a cada 2^3=8
endereços, ou seja: 0, 8, 16, 24, ... 248.

Os endereços de broadcast serão 7, 15, 23, 31, ... 255.

Os endereços de hosts da rede 0 serão de 1 a 6, e assim por diante.

**Sub-redes com máscara 29 bits**
| Endereço da rede | Estações (hosts) | Endereço de Broadcast |
|----|----|----|
| x.x.x.0 | x.x.x.1 a x.x.x.6 | x.x.x.7 |
| x.x.x.8 | x.x.x.9 a x.x.x.14 | x.x.x.15 |
| x.x.x.16 | x.x.x.17 a x.x.x.22 | x.x.x.23 |
| x.x.x.24 | x.x.x.25 a x.x.x.30 | x.x.x.31 |
| .... | .... | .... |
| x.x.x.248 | x.x.x.249 a x.x.x.254 | x.x.x.255 |


#### Máscara /30 = 255.255.255.252
(11111100) = 128+64+32+16+8+4

No último byte temos 6 bits 1 e 2 bits 0.

Essa máscara pode representar (2)^6 = 64 sub-redes, cada uma com (2)^2 – 2 = 2 hosts.

Seguindo as regras acima, r=6, h=8-6=2, as redes serão a cada 2^2=4
endereços, ou seja: 0, 4, 8, 12, 16, ... 252.

Os endereços de broadcast serão 3, 7, 11, 15, 19, ... 255.

Os endereços de hosts da rede 0 serão de 1 e 2, e assim por diante.

**Sub-redes com máscara 30 bits**
| Endereço da rede | Estações (hosts) | Endereço de Broadcast |
|----|----|----|
| x.x.x.0 | x.x.x.1 e x.x.x.2 | x.x.x.3 |
| x.x.x.4 | x.x.x.5 e x.x.x.6 | x.x.x.7 |
| x.x.x.8 | x.x.x.8 e x.x.x.9 | x.x.x.11 |
| x.x.x.12 | x.x.x.13 e x.x.x.14 | x.x.x.15 |
| .... | .... | .... |
| x.x.x.252 | x.x.x.253 e x.x.x.254 | x.x.x.255 |

Observe que a criação de uma máscara de rede de 31 bits implicaria em deixar somente dois endereços para cada rede. Mas o primeiro é o endereço da rede e o último é reservado para broadcast. 

Assim, não sobram endereços disponíveis para máquinas. 
Por isso, a máscara de rede de 31 bits não é usada.

Quando usamos uma máscara de rede de 32 bits, a interpretação é diferente, 
e não estamos fazendo referência a uma rede, e sim a um único host.
Portanto, o último byte dos netmasks possíveis para dividir uma rede classe C em sub-redes 
são 0, 128, 192, 224, 240, 248 e 252. O final 255 já indica um host.