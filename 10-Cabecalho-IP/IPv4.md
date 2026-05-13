# O cabeçalho IP

Há duas versões do protocolo IP em uso atualmente. A versão 4 (IPv4), que foi a versão
que tornou o protocolo IP bastante popular, e a versão 6 (IPv6), lançada algumas décadas
mais tarde para resolver algumas limitações da versão 4.

---

## Cabeçalho IPv4

O IPv4 é um protocolo aberto desenvolvido de forma colaborativa por organizações da indústria, governos e centros de pesquisa, sob coordenação da **Internet Engineering Task Force.**
As especificações são publicadas em documentos chamados RFCs (Request for Comments).

O IPv4 foi definido inicialmente em 1980 pela RFC 760 e atualizado em 1983 pela RFC 791. Mesmo com a expansão do IPv6, ele ainda é amplamente utilizado na Internet.

Cada pacote IPv4 possui um cabeçalho responsável por transportar informações de controle necessárias para o roteamento e entrega dos dados.

Essa versão ainda está em uso em grande parte da Internet, sendo gradualmente
migrada para a IPv6, detalhada no próximo capítulo.

O cabeçalho inserido em cada pacote IPv4 possui pelo menos **5 palavras de 32 bits**(4
bytes), totalizando 20 bytes

![IPv4](/10-Cabecalho-IP/img/figura1.png)

* **Versão(4 bits):** Indica a versão do protocolo IP utilizada, normalmente IPv4 ou IPv6.

* **IHL – Internet Header Length(4 bits):** Informa o tamanho do cabeçalho em palavras de 4 bytes, pois o IPv4 permite cabeçalhos maiores quando existem opções adicionais.

* **Serviços Diferenciados - DS(8 bits):** Usado para definir classes de serviço e prioridades de tráfego (QoS). Permite diferenciar aplicações como voz, vídeo e transferência de arquivos, oferecendo diferentes níveis de prioridade e desempenho.

* **Tamanho Total(16 bits):** Indica o tamanho completo do pacote, incluindo cabeçalho e dados, podendo chegar a 65.535 bytes.

* **Identificação(16 bits):** Identifica fragmentos pertencentes ao mesmo datagrama IP quando ocorre fragmentação.

* **DF – Don’t Fragment(1 bit):** Indica que o pacote não deve ser fragmentado. Caso a rede não suporte o tamanho do pacote, ele será descartado e uma mensagem de erro será enviada.

* **MF – More Fragments(1 bit):** Indica se ainda existem mais fragmentos do mesmo datagrama. Todos os fragmentos possuem bit = 1, exceto o último.

* **Fragment Offset(13 bits):** Informa a posição do fragmento dentro do datagrama original para permitir a remontagem correta.

* **TTL – Time To Live(8 bits):** Limita a quantidade de roteadores (saltos/hops) pelos quais o pacote pode passar. A cada roteador o valor é decrementado, quando chega a 0, o pacote é descartado para evitar loops infinitos. E é enviada uma mensagem de erro para a origem

* **Protocolo(8 bits):** Informa qual protocolo de transporte receberá os dados no destino, como TCP ou UDP.

* **Checksum do Cabeçalho(16 bits):** Verifica a integridade do cabeçalho IP. O valor é recalculado em cada roteador porque o TTL é alterado durante o percurso.

* **Tamanho total(16 bits):** Especifica o tamanho total do pacote, incluindo o cabeçalho e os
dados. Por ter 16 bits, permite pacotes de até 65.535 bytes (64KB).

**Endereço de origem - Source address** e **Endereço de destino - Destination address**(32
bits): São os endereços IP da máquina de origem e da máquina de destino.

* **Opções (tamanho variável, sempre múltiplo de 4 bytes):** Foi projetado para permitir
extensões futuras do protocolo, além de 5 opções já previstas originalmente:
    - **Security:** Especifica o nível de segurança do datagrama
    - **Strict source routing:** Mostra o caminho completo a ser seguido
    - **Loose source routing:** Apresenta uma lista de roteadores que devem estar no caminho
    - **Record route:** Registra a rota (cada roteador no caminho anexa o seu endereço IP)
    - **Timestamp:** Cada roteador anexa o seu endereço e o seu registro de tempo (data e hora)