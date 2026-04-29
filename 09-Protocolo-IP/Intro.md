# Protocolo IP

## Introdução

O protocolo IP é o principal protocolo da arquitetura TCP/IP e atua na camada de rede, sendo responsável por identificar dispositivos na rede por meio do endereçamento IP e encaminhar pacotes até o destino através do roteamento.

O IP foi desenvolvido durante a Guerra Fria com foco em resistência a falhas de comunicação. Por isso, ele funciona de forma sem conexão e orientada a datagramas, onde cada pacote é enviado de maneira independente e contém todas as informações necessárias para chegar ao destino.

Essa característica traz algumas consequências:

os pacotes podem chegar fora de ordem;
alguns pacotes podem ser perdidos;
diferentes pacotes podem seguir rotas diferentes.

O protocolo IP oferece um serviço de “melhor esforço”, tentando entregar os pacotes, mas sem garantir entrega, tempo ou ordem. Quando é necessária confiabilidade na transmissão, utiliza-se o protocolo TCP, que complementa o IP garantindo controle e entrega correta dos dados.

---

## Exercicio Resolvido

### Suponha que você tenha um dispositivo com a seguinte configuração: IP: 192.168.10.150, Netmask: 255.255.255.224.
**a) Qual o endereço de rede desse dispositivo (NetID)?**
Para obter o NetID, pode-se fazer o AND lógico entre o IP e o Netmask, ou
procurar na tabela correspondente ao Netmask.
**1ª forma:** Fazendo o AND lógico: Os três primeiros bytes do netmask são 255.
Assim, os três primeiros bytes do NetID serão iguais aos do IP: 192.168.10.
O último byte do Netmask não é nem 0 nem 255, então precisa fazer bit a bit.

150 = 128 + 16 + 4 + 2 = 1001 0110.

224 = 128 + 64 + 32 = **111**0 0000.

Fazendo o AND lógico, temos: **100**0 0000 = 128.

Assim, o NetID é 192.168.10.128.
**2ª forma:** Olhando na tabela /27 (255.255.255.224), observamos que o
endereço do host 150 está **entre 129 e 158**, portanto, pertence à subrede 128.
Assim, o NetID será 192.168.10.128.

**b) Qual o endereço de Broadcast dessa rede?**
Olhando na tabela, uma vez que já localizamos o NetID, o **Broadcast é o último endereço** 
antes da próxima rede. Nesse caso, **192,168.10.159**.
A outra forma de fazer é fazendo o AND lógico, e colocando todos os bits de
host em 1.

150 = 128 + 16 + 4 + 2 = 1001 0110.

224 = 128 + 64 + 32 = 111**0 0000**.

Fazendo o AND lógico, temos: NetID → 100**0 0000** = 128.

Passando os últimos 5 bits para 1, temos que o Broadcast é 100**1 1111** = 159
Assim, o Broadcast é 192.168.10.159.

**c) Quais endereços de hosts estão na mesma rede do dispositivo?**
Todos os endereços que estão entre o NetID e o Broadcast.
Nesse caso, de 192.168.10.129 a 192.168.10.158.
Isso pode ser obtido olhando na tabela, ou calculando o NetID e o Broadcast.
Lembre que os três primeiros bytes precisam ser iguais aos do IP, sempre que o
Netmask tem mais de 24 bits.