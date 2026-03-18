# Introdução às Redes de Computadores  

## Apresentação  
Um computador isolado acessa apenas seus próprios dispositivos de armazenamento (HD, SSD, pendrive, CD, DVD), o que limita a atualização e o compartilhamento de informações.  

Já um computador conectado a uma rede pode dispor de acesso aos dados dos outros
computadores conectados a essa mesma rede. Isso amplia muito a disponibilidade das
informações. Quanto maior o tamanho da rede, maior a quantidade de dados disponíveis.

Redes de computadores são formadas por:  
- **Hardware** (computadores e equipamentos de comunicação);  
- **Software de rede** (protocolos que permitem a comunicação);  
- **Meios de comunicação** (responsáveis pelo transporte dos dados).  

---

## 1. Histórico  
Inicialmente, os computadores funcionavam isoladamente, com troca de informações feita por digitação ou transporte físico de mídias (como fitas magnéticas).  

Com o crescimento das organizações, surgiu a necessidade de acesso remoto, inicialmente via conexão telefônica.  

Os fabricantes criaram soluções próprias para interligar seus equipamentos, mas eram incompatíveis entre si. Isso exigia múltiplos programas específicos para permitir comunicação entre diferentes marcas, aumentando a complexidade.  

Essa dificuldade levou à necessidade de **padronização dos protocolos de rede**.  

---

## 2. Importância das Redes de Computadores  

Principais benefícios:  

- **Compartilhamento de recursos:** acesso de todos os computadores da rede aos
dados e dispositivos que existem dentro da organização.
- **Aumento da confiabilidade:** possibilidade de cópias de segurança e maior continuidade de serviços críticos (militares, bancários, industriais, etc.).  
- **Redução de custos:** uso de computadores pessoais, compartilhamento de recursos e computação em nuvem.  
- **Redução da redundância de dados:** evita múltiplas cópias desatualizadas, especialmente em bancos de dados e aplicações web.  

---

## 3. Classificação das Redes  

### 3.1 Alcance  

Classificação conforme a área de cobertura:  

1. **PAN (Personal Area Network):** alcance de 1 a 10 metros. Ex.: Bluetooth e ZigBee.  

2. **LAN (Local Area Network):** cobre ambientes como casas e edifícios. Ex.: Ethernet e Wi-Fi.  

3. **MAN (Metropolitan Area Network):** redes metropolitanas (centenas de metros até dezenas de km). Tecnologias como ADSL, FTTH, 3G, 4G e 5G.  

4. **WAN (Wide Area Network):** redes de longa distância (acima de 100 km), utilizando fibra óptica, micro-ondas, satélites e cabos submarinos.  

---

### 3.2 Tipo de ligação  

1. **Ponto-a-ponto:** conecta dois dispositivos diretamente. Pode usar roteadores intermediários. Comum em redes de longa distância.  

2. **Multiponto (difusão):** meio físico compartilhado entre várias estações. Exige controle de acesso para evitar conflitos.  

---

### 3.3 Topologias  

Organização das conexões físicas e lógicas da rede:  

1. **Barramento:** todos os dispositivos conectados a um único cabo. Simples, mas permite apenas uma transmissão por vez.  
![Barramento 1](/01-Introducao/img/figura1.png)
![Barramento 2](/01-Introducao/img/figura2.png)

2. **Anel:** dispositivos conectados em círculo. Se houver rompimento, a rede pode parar.  
![Anel](/01-Introducao/img/figura3.png)

3. **Estrela:** todos conectados a um equipamento central. Muito usada atualmente. Se o equipamento central falhar, a rede para; se um computador falhar, os demais continuam funcionando.  
![Estrela](/01-Introducao/img/figura4.png)

---

### 3.4 Sentido  

1. **Simplex:** comunicação em um único sentido (ex.: rádio e TV).  
2. **Half-duplex:** comunicação nos dois sentidos, mas não simultaneamente (ex.: rádio comunicador, redes Wi-Fi).  
3. **Full-duplex:** comunicação simultânea nos dois sentidos (ex.: telefonia, Ethernet moderna).  

---

### 3.5 Paralelismo  

1. **Transmissão paralela:** múltiplos canais enviam vários bits simultaneamente (usado em curtas distâncias, como barramentos internos).  

2. **Transmissão serial:** envio de bits um a um em um único canal. É o padrão nas redes atuais. Velocidades são medidas em bits por segundo (bps).  

Exemplo: 1 MB (megabyte) equivale a 8 Mb (megabits), o que impacta o tempo de download conforme a taxa de transmissão (Mbps).
