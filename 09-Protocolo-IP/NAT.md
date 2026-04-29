# Protocolo IP

## NAT (Network Address Translation)
A Tradução de Endereços de Rede (NAT - Network Address Translation) é um artifício 
utilizado para esconder uma rede inteira atrás de um único endereço IP público.
O NAT foi criado para permitir a expansão do número de computadores na Internet
mesmo diante do iminente esgotamento dos endereços IPv4

### Endereços IP privados
A implementação do NAT foi possível porque foram reservadas três faixas de endereços IP 
(uma em cada classe de endereçamento) chamados de endereços IPs privados.
Eles não foram distribuídos para nenhuma empresa, e os roteadores da Internet 
não contém rotas para esses endereços.

#### Faixas de IPs Privados
| Classe | NetID | 1º Host | Último Host | Broadcast | Netmask |
|----|----|----|----|----|----|
| **A** | 10.0.0.0 | 10.0.0.1 | 10.255.255.254 | 10.255.255.255 | 255.0.0.0 (/8) |
| **B** | 172.16.0.0 | 172.16.0.1 | 172.31.255.254 | 172.31.255.255 | 255.240.0.0 (/12) |
| **C** | 192.168.0.0 | 192.168.0.1 | 192.168.255.254 | 192.168.255.255 | 255.255.0.0 (/16) |

Observe que essas faixas incluem uma rede classe A (a rede 10.0.0.0/8),
16 redes classe B (as redes 172.16.0.0/16 até 172.31.0.0/16) e 256 redes
classe C (as redes 192.168.0.0/24 até 192.168.255.0/24)
Qualquer endereço IP que esteja em uma dessas três faixas é considerado IP privado. 

**Qualquer outro IP que não esteja dentro dessas três faixas é considerado IP público.**

Os endereços IP privados podem ser usados livremente em redes internas, como residências ou empresas. Porém, para que esses dispositivos consigam acessar a Internet, é necessário utilizar o serviço NAT

O NAT funciona em um roteador que possui:
* IP privado conectado à rede interna;
* IP público conectado à Internet.

Quando um computador da rede interna envia dados para a Internet, o NAT substitui o endereço IP privado de origem pelo IP público do roteador. O roteador registra essa tradução em uma tabela associando também as portas de comunicação.

![exemplo NAT](/09-Protocolo-IP/img/figura2.png)

Quando a resposta retorna da Internet:
Ela **chega ao IP público** do roteador, o **NAT consulta** sua tabela substituindo o endereço de destino pelo **IP privado correto**, e **encaminha o pacote ao dispositivo** interno correspondente.

Com isso, vários dispositivos podem compartilhar um único IP público para acessar a Internet.
Além de economizar endereços IPv4 públicos, o NAT também aumenta a segurança da rede interna, pois computadores externos não conseguem acessar diretamente os dispositivos protegidos atrás do roteador NAT.