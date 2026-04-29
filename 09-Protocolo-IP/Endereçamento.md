# Protocolo IP

## Endereçamento IP

O endereço IPv4 identifica de forma única cada dispositivo conectado à Internet. Ele possui 32 bits (4 bytes) e é representado por quatro números de 0 a 255 separados por pontos, como 192.168.0.1.

O endereço IP é dividido em:

* **NetID:** identifica a rede;
* **HostID:** identifica o dispositivo dentro da rede.

A quantidade de bits usada para cada parte é definida pela máscara de rede (Netmask), que pode ser representada:

pelo formato CIDR, como /24;
ou em decimal, como 255.255.255.0.

Quanto mais bits forem usados para o NetID, maior será o número de redes possíveis e menor será a quantidade de hosts por rede.

![redes e hosts](/09-Protocolo-IP/img/figura1.png)

Inicialmente, o IPv4 utilizava classes de endereçamento:

* **Classe A:**
    - primeiro bit = 0
    - faixa: 0 a 127 no primeiro byte
    - máscara padrão: /8
    - grande quantidade de hosts.
* **Classe B:**
    - primeiros bits = 10
    - faixa: 128 a 191
    - máscara padrão: /16.
* **Classe C:**
    - primeiros bits = 110
    - faixa: 192 a 223
    - máscara padrão: /24.
* **Classe D:**
    - primeiros bits = 1110
    - faixa: 224 a 239
    - usada para multicast.
* **Classe E:**
    - primeiros bits = 1111
    - faixa: 240 a 255
    - reservada para testes e uso futuro.

O endereço 127.0.0.1 é reservado para loopback, usado para comunicação da máquina consigo mesma.

#### Tabela

| Classe | 1º Endereço | Ultimo endereço | NetMask| netmask | Nº de Redes | Nº de Endereços de cada rede |
|------|-----|-----|-----|-----|-----|-----|
| **A** | 0.0.0.0 | 127.255.255.255 | 255.0.0.0 | /8 | 2^7 = 128 | 2^24 = 16.777.216 |
| **B** | 128.0.0.0 | 191.255.255.255 | 255.255.0.0 | /16 | 2^14 = 16.384 | 2^16 = 65.536 | 
| **C** | 192.0.0.0 | 223.255.255.255 | 255.255.255.0 | /24 | 2^21 = 2.097.152 | 2^8 = 256 |
| **D** | 224.0.0.0 | 239.255.255.255 | Multicast | | | |
| **E** | 240.0.0.0 | 255.255.255.255 | Testes IETF | | | |

### Endereço Broadcast

Os primeiros bits do endereço representam a rede (NetID) e os últimos representam o host (HostID).

Em cada rede existem dois endereços reservados:

* **Endereço da rede:** quando todos os bits do HostID são 0;
* **Endereço de broadcast:** quando todos os bits do HostID são 1.

O endereço de broadcast é usado para enviar mensagens para todos os dispositivos da rede ao mesmo tempo. Por isso, nem o primeiro nem o último endereço da rede podem ser atribuídos a hosts.


### Distribuição de IP 

O IPv4 foi criado em 1969 pela ARPA, quando não se imaginava o enorme crescimento da Internet. O protocolo usa 32 bits, permitindo cerca de 4 bilhões de endereços.

Porém, o sistema de classes (A, B e C) gerou desperdício de endereços, principalmente porque muitas empresas e universidades receberam grandes blocos de IPs sem necessidade. Com o crescimento da Internet, computadores pessoais e da web nos anos 1990, surgiu o risco de esgotamento dos endereços IPv4.

Para adiar esse problema, foram criadas duas soluções:

* **CIDR:** melhor aproveitamento dos blocos de endereços;
* **NAT:** permite que vários dispositivos compartilhem um único IP público.

Os endereços públicos da Internet são administrados pelo **IANA** (Internet Assigned Numbers Authority - `www.iana.org`). 
Conforme a necessidade, os blocos são distribuídos para as autoridades regionais. 
Para a América Latina e Caribe é o **LACNIC** (Latin America and Caribbean Network Information Centre).

Posteriormente, foi desenvolvido o IPv6, com 128 bits de endereçamento, oferecendo uma quantidade muito maior de endereços e resolvendo o problema de escassez do IPv4.

### Comunicação entre dispositivos
Em uma rede IP, dois dispositivos conseguem se comunicar se estão na mesma rede. 
Para saber qual é a rede de um dispositivo, basta fazer o **AND** lógico **entre o endereço IP e o Netmask.**
Exemplo: Suponha um dispositivo com o IP 192.168.1.101, e Netmask 255.255.255.0. 
Para encontrar o endereço de rede, fazemos o AND lógico.
Lembrando que o AND lógico, de dois bits só dá 1 se os dois forem 1.

192 = 128 + 64

168 = 128 + 32 + 8

101 = 64 + 32 + 4 + 1

| IP | 192 <br> 1 1 0 0 0 0 0 0 | 168 <br> 1 0 1 0 1 0 0 0 | 1 <br> 0 0 0 0 0 0 0 1 | 101 <br> 0 1 1 0 0 1 0 1| 
|----|----|----|----|----|
| **Netmask** |1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 1 1 1 1 1 1 1 1 | 0 0 0 0 0 0 0 0 |
| **NetID** | 1 1 0 0 0 0 0 0 <br> 192 | 1 0 1 0 1 0 0 0 <br> 168 | 0 0 0 0 0 0 0 1 <br> 1 | 0 0 0 0 0 0 0 0 <br> 0 |
