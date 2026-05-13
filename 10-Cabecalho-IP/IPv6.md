# O cabeçalho IP

Há duas versões do protocolo IP em uso atualmente. A versão 4 (IPv4), que foi a versão
que tornou o protocolo IP bastante popular, e a versão 6 (IPv6), lançada algumas décadas
mais tarde para resolver algumas limitações da versão 4.

---

## Cabeçalho IPv6

O IPv6 é a versão mais recente do protocolo IP, criada para resolver as limitações do IPv4, principalmente a escassez de endereços IP causada pelo crescimento da Internet e do uso de computadores pessoais.

Seu desenvolvimento começou nos anos 1990, e sua principal especificação está na RFC 2460, publicada em 1998.

Além de ampliar enormemente a capacidade de endereçamento, o IPv6 também trouxe melhorias de desempenho e eficiência:
* cabeçalho foi simplificado
* vários campos foram removidos ou reorganizados
* processamento nos roteadores foi reduzido

Uma mudança importante foi a remoção do campo de checksum do cabeçalho. Como as redes modernas, especialmente as de fibra óptica, são mais confiáveis, tornou-se desnecessário recalcular esse valor em cada roteador, reduzindo a carga de processamento e aumentando o desempenho da rede.

O IPv6 também foi projetado pensando em Qualidade de Serviço (QoS), importante para aplicações sensíveis a atraso, como: chamadas de voz (VoIP), videoconferências, jogos online e transmissões multimídia.

Os campos Traffic Class e Flow Label, em conjunto com os endereços de origem e destino permitem a classificação dos pacotes de acordo com o serviço contratado e previamente configurado nos roteadores da rede.

![IPv6](/10-Cabecalho-IP/img/figura2.png)

O cabeçalho IP tem 10 palavras de 32 bits, totalizando 320 bits ou 40 bytes,
contendo 8 campos

* **Version(4 bits):** Indica a versão do protocolo IP utilizado.

* **Traffic Class(8 bits):** Define a classe de serviço do pacote, permitindo priorizar diferentes tipos de tráfego, como voz, vídeo ou transferência de arquivos. É utilizado na arquitetura de Serviços Diferenciados (QoS), semelhante ao campo DS do IPv4.

* **Flow Label(20 bits):** Identifica pacotes que pertencem ao mesmo fluxo de comunicação entre origem e destino. Isso permite que a rede trate esses pacotes da mesma maneira, melhorando o gerenciamento de QoS. Cada fluxo é identificado por um endereço de origem, um endereço de destino e um número de fluxo.
Assim, é possível gerenciar até 220 fluxos ativos simultaneamente entre dois endereços IP específicos

* **Payload Length (16 bits):** Informa o tamanho dos dados transportados após o cabeçalho IPv6 de 40 bytes. Diferente do IPv4, esse valor não inclui o tamanho do cabeçalho. O IPv6 pode transportar até 65.535 bytes de dados úteis.

* **Next Header(8 bits):** Substitui o campo “Protocolo” do IPv4. Indica o próximo cabeçalho de extensão, caso exista, ou o protocolo de transporte utilizado, como TCP ou UDP.

* **Hop Limit(8 bits):** Equivalente ao TTL do IPv4. Define o número máximo de roteadores (saltos/hops) que o pacote pode atravessar. O valor é reduzido a cada roteador e, quando chega a 0, o pacote é descartado para evitar loops de roteamento.

* **Source Address - Endereço de origem:** Campo de 128 bits que indica o endereço IP da 
máquina de origem do pacote.

* **Destination Address - Endereço de destino:** Campo de 128 bits que indica o endereço IP
da máquina de destino do pacote.

### Notação do endereçamento IPv6

A representação dos endereços também mudou. Os 16 bytes são representados em 8
grupos de 2 bytes, ou 4 dígitos hexadecimais (cada byte pode ser representado por dois
dígitos hexadecimais), separados por pelo sinal de dois pontos (":"), como no exemplo a
seguir:

`8000:0000:0000:0000:0123:4567:89AB:CDEF`

Essa é a notação exibindo todos os bytes do endereço. Mas como existem muitos bytes
zerados, existem outras três alternativas para exprimir o endereço de modo mais
compacto.

1. **Omitindo os zeros à esquerda**

O endereço 0000:0000:0000:0000:0123:4567:89AB:CDEF pode ser expresso como:

`0123:4567:89AB:CDEF`

2. **Substituindo um ou mais grupos de 16 bits 0 por "::"**

O endereço 8000:0000:0000:0000:0123:4567:89AB:CDEF pode ser expresso como:

`8000::0123:4567:89AB:CDEF`

Observe que o "::" só pode ser usado uma vez no endereço. Caso contrário não seria
possível saber quantos conjuntos de zeros estão sendo omitidos em cada sinal "::".

3. **Representação do IPv4**

Os endereços IPv4 podem ser expressos usando o sinal "::" seguido do endereço
decimal tradicional. 
Exemplo:

`::192.168.0.1`