# Arquiteturas de Redes  

## Introdução  
Para que haja comunicação entre dispositivos, é necessário que todos sigam as mesmas regras, chamadas **protocolos**, que definem formato e sequência das mensagens.  

Inicialmente, fabricantes criavam soluções próprias, gerando incompatibilidades. A necessidade de interligar equipamentos de diferentes fabricantes levou à criação de **padrões de comunicação**.

---

# Arquitetura TCP/IP

## Histórico  
Durante a Guerra Fria, o Departamento de Defesa dos EUA solicitou à **DARPA**(Defense Advanced Research Project
Agency, ou agência de projetos de pesquisa avançados de defesa) o desenvolvimento de uma rede robusta, capaz de continuar operando mesmo com falhas em nós intermediários.

Isso levou à criação dos protocolos **TCP/IP**.

Inicialmente esse conjunto de protocolos foi utilizado para a conexão entre os centros de pesquisa da DARPA, sendo conhecida como ARPANET (Advanced Research Projects
Agency Networks). Pouco a pouco, centenas de universidades e repartições públicas foram
conectadas à rede, utilizando inicialmente linhas telefônicas dedicadas e depois conexões de rádio e de satélite.
A partir da fusão da ARPANET com a NFSNET (rede mantida pela NSF –
National Science Foundation), a rede passou a ser chamada Internet.

O padrão TCP/IP tornou-se dominante, enquanto o OSI passou a ser usado principalmente como modelo didático.

---

## Estrutura da Arquitetura TCP/IP  

Diferente do OSI, possui **4 camadas**:
![Figura 2](/02-Arquiteturas/figura2.png)

### 1. Camada de Enlace(Interface de Rede)
Interface com tecnologias de rede existentes.  
Não define protocolos específicos, mas uma
interface de conexão com as tecnologias de comunicação ou de rede local existentes.

### 2. Camada Internet(Camada de Redes)
Roteamento (repasse, encaminhamento) dos pacotes da máquina de origem até a máquina de destino, possivelmente em outra rede local.

* **IP(Internet Protocol):** trabalha sem conexão, orientado a Datagramas (comutação por pacotes). Assim, cada datagrama é roteado independentemente dos anteriores
* **ICMP:** serve para enviar mensagens de controle, como teste de
conectividade ou alertas de pacotes expirados.
* Cada computador na Internet precisa ter o seu endereço IP individual.

### 3. Camada de Transporte  
Fornecem um meio de comunicação
de ponta a ponta, da mesma forma que a camada de transporte do modelo OSI.

* **TCP(Transmission Control Protocol):** realiza todos os controles para recuperar eventuais falhas das camadas inferiores
* **UDP(User Datagram Protocol):** comunicação mais leve e rápida, mas sujeita a eventuais perdas de dados


### 4. Camada de Aplicação  
Reúne funções de aplicação, sessão e apresentação do modelo OSI.  
Os protocolos são fornecidos pelos programas que usam o TCP/IP para comunicação.
Cada aplicação pode fazer uso de um ou mais protocolos, e cada
protocolo pode ser específico de uma aplicação ou ser usado por várias aplicações.

![FIgura 3](/02-Arquiteturas/figura3.png)

---

# Conclusão  

- O **Modelo OSI** é um padrão conceitual de 7 camadas, usado principalmente para estudo.  
- A **Arquitetura TCP/IP** é mais simples e prática, sendo o padrão real da Internet.  
- Atualmente, o ensino de redes utiliza o OSI como referência teórica e o TCP/IP como base prática.