# Transmissões

## Alocação e Banda ISM

O uso do espectro eletromagnético precisa ser **controlado para evitar interferências**, por isso serviços como rádio e TV pagam pela concessão de frequências. No entanto, existem **bandas livres chamadas ISM**, destinadas a usos industriais, científicos e domésticos sem necessidade de licença.

Essas bandas são amplamente utilizadas por dispositivos como **Wi-Fi, Bluetooth, telefones sem fio** e outros aparelhos. **A faixa de 2,4 GHz é a mais comum**, mas sofre bastante interferência; já a de 5,8 GHz é menos utilizada e mais “limpa”.

Como vários **dispositivos compartilham as mesmas frequências**, podem **ocorrer interferências** entre eles, especialmente **se não houver padrões de coexistência**, como acontece em alguns equipamentos mais antigos ou não padronizados.

---

## Por Radio

As ondas de rádio são amplamente usadas na comunicação por serem **fáceis de gerar**, alcançarem longas distâncias e atravessarem obstáculos, como prédios. Elas se propagam em todas as direções, não exigindo alinhamento preciso entre transmissor e receptor.

Seu comportamento varia com a frequência: **em baixas frequências, atravessam melhor obstáculos**, mas perdem potência com a distância; em altas frequências, **propagam-se em linha reta, sofrem mais reflexões** e podem ser absorvidas por chuva e objetos. Além disso, estão sujeitas a interferências elétricas.

![diferença baixas x altas](/05-Meios-Fisicos-II/img/figura2.png)

Diferente dos meios guiados, a **perda de sinal no rádio depende da distância dobrada** (ex.: queda de 6 dB), permitindo maior alcance, mas exigindo controle governamental do uso das frequências.

Nas **bandas mais baixas (VLF, LF, MF)**, as ondas **seguem a curvatura da Terra** e atravessam bem edifícios, porém têm baixa largura de banda. Já nas **bandas HF e VHF**, podem ser **refletidas pela ionosfera**, possibilitando comunicações a longas distâncias, como em rádios amadores e aplicações militares.

---

## Por Micro-ondas

As micro-ondas **(acima de 100 MHz)** se propagam em **linha reta e podem ser concentradas em feixes estreitos**, geralmente com **antenas parabólicas**, proporcionando melhor qualidade de sinal, mas exigindo alinhamento preciso entre transmissor e receptor.

Frequências **mais altas têm maior dificuldade** para atravessar obstáculos e podem ser afetadas pela chuva, especialmente acima de 4 GHz. No Wi-Fi, as **frequências mais comuns são 2.4 GHz** (maior alcance e mais interferência) e **5.8 GHz** (menos interferência, porém menor alcance e maior sensibilidade a obstáculos e umidade).

Além disso, micro-ondas são usadas para **conexões de longa distância entre torres**, sendo uma alternativa mais rápida e econômica à instalação de fibra óptica em certos cenários.

---

## Optica

A transmissão óptica sem fio **utiliza luz (infravermelho, visível ou ultravioleta)** para enviar dados. É comum em curtas distâncias, como em controles remotos, sendo barata, simples e confiável. Como a **luz não atravessa objetos opacos**, o alcance é limitado, mas isso também aumenta a segurança e evita interferências.

![FSO](/05-Meios-Fisicos-II/img/figura11.png)

Uma aplicação importante é a **FSO (Óptica de Espaço Livre)**, que conecta redes entre edifícios usando feixes de laser ou LED. Esse método oferece alta largura de banda, boa segurança e dispensa licença regulatória, mas exige alinhamento preciso entre os dispositivos.

Apesar das vantagens, a transmissão óptica é **sensível a fatores como chuva, neblina, vento e vibrações**, além da **dificuldade de manter o feixe alinhado**. Ainda assim, pode **atingir altas velocidades** (até dezenas de Gbps) e distâncias de **até alguns quilômetros**.