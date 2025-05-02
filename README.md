# PROJETO DE RELÓGIO DIGITAL COM LED

**Data:** 11/04/2025

**Instituição:** Pontifícia Universidade Católica de Campinas
**Curso:** Engenharia Elétrica
**Disciplina:** PI: Lógica e Circuitos Lógicos
**Professor:** Prof. Frank

**Participantes do grupo:**

* Felipe Grolla Freitas - RA: 24004846
* Guilherme Oliveira Nogueira - RA: 25006542
* Giovana - RA:
* Henrique - RA:

**Local e Ano:** CAMPINAS — SP, 2025

## 1. INTRODUÇÃO

O projeto de um relógio digital com visualização por meio de displays de LED representa uma aplicação prática e integrada de diversos conceitos fundamentais da engenharia elétrica, em especial nas áreas de eletrônica analógica e digital. Este relatório apresenta o desenvolvimento completo de um circuito capaz de realizar a contagem e exibição contínua de horas, minutos e segundos, utilizando exclusivamente componentes discretos de lógica digital, sem a utilização de microcontroladores ou qualquer tipo de programação. Toda a lógica do sistema foi construída com flip-flops do tipo JK, decodificadores binário-para-7 segmentos, portas lógicas (AND, OR, NOT, NAND), multiplexadores (MUX) e circuitos de divisão de frequência, configurados para gerar os pulsos de clock necessários para a temporização do sistema. Além da lógica digital, foi necessário aplicar conhecimentos de eletrônica analógica para o tratamento e condicionamento do sinal de entrada, como no dimensionamento e montagem de uma fonte de alimentação retificadora com filtragem capacitiva, garantindo estabilidade na alimentação dos circuitos lógicos. Também foram aplicadas técnicas de atraso e sincronização de sinal, fundamentais para evitar erros de transição e garantir a precisão temporal da contagem. O projeto foi desenvolvido no ambiente de laboratório do curso de Engenharia Elétrica da PUC Campinas, como parte de uma atividade prática voltada à consolidação dos conteúdos estudados em disciplinas de circuitos digitais e eletrônica básica. A construção do relógio, totalmente baseada em hardware, proporcionou uma rica experiência de integração entre teoria e prática, permitindo ao aluno vivenciar desafios reais de projeto, montagem e análise de sistemas digitais completos.

## 2. OBJETIVO

O principal objetivo deste projeto foi desenvolver um relógio digital funcional, capaz de realizar a contagem precisa de horas, minutos e segundos, utilizando exclusivamente circuitos eletrônicos discretos e componentes de lógica digital, sem o uso de linguagens de programação ou microcontroladores. Com isso, buscou-se aplicar de forma prática os conhecimentos adquiridos em disciplinas de Eletrônica e Circuitos Digitais, com foco na construção de um sistema completo de temporização e exibição em displays de LED de sete segmentos.

Entre os objetivos específicos do projeto, destacam-se:

* Projetar e implementar uma fonte de alimentação retificadora com filtragem adequada para alimentar os circuitos digitais;
* Elaborar um sistema de geração de clock utilizando circuitos de atraso e divisão de frequência para fornecer pulsos estáveis;
* Desenvolver contadores síncronos e assíncronos utilizando flip-flops JK para a contagem de unidades e dezenas de segundos, minutos e horas;
* Integrar decodificadores binários para 7 segmentos com os contadores, permitindo a visualização correta dos valores temporais;
* Utilizar multiplexadores e lógica combinacional para controle e distribuição adequada dos sinais no circuito.

Ao final do projeto, esperava-se que o sistema fosse capaz de operar de maneira contínua, estável e precisa, representando corretamente o tempo em formato digital com atualização em tempo real nos displays de LED.

## 3. METODOLOGIA

A metodologia adotada para o desenvolvimento do relógio digital com LED baseou-se em uma abordagem sequencial, estruturada em etapas interdependentes, desde a análise teórica dos circuitos envolvidos até a montagem prática e testes funcionais em laboratório. O projeto foi conduzido de forma inteiramente baseada em hardware, utilizando componentes eletrônicos discretos e circuitos digitais clássicos, o que exigiu planejamento detalhado e validação cuidadosa de cada subsistema. Inicialmente, foi realizado um estudo teórico dos principais blocos funcionais necessários: fonte de alimentação, gerador de clock, contadores, decodificadores e circuitos de exibição. Essa etapa incluiu a revisão de conceitos como retificação e filtragem de corrente alternada, operação de flip-flops JK, lógica de contagem binária, decodificação para displays de sete segmentos e técnicas de multiplexação. Com base nesse estudo, os circuitos foram esquematizados em etapas modulares:

* **Fonte Retificadora:** conversão de corrente alternada em corrente contínua utilizando diodos e capacitores, com dimensionamento adequado à tensão e corrente exigidas pelos circuitos lógicos.
* **Gerador de Clock e Circuito de Atraso:** criação de uma base de tempo estável utilizando divisores de frequência e filtros RC para controle dos pulsos.
* **Contadores e Registradores:** implementação de contadores binários síncronos com flip-flops JK para a contagem de segundos, minutos e horas, com resets automáticos configurados para 60 segundos/minutos e 24 horas.
* **Decodificadores e Display:** uso de circuitos decodificadores BCD para 7 segmentos conectados aos contadores, permitindo a exibição em displays comuns cátodo.
* **Distribuição Lógica e MUX:** aplicação de multiplexadores e lógica combinacional para seleção e controle dos sinais enviados aos displays.

Cada etapa foi testada individualmente para validação de seu funcionamento antes da integração total do sistema. O processo de montagem utilizou protoboard inicialmente, seguido de montagem definitiva em placa padrão com solda, garantindo robustez e estabilidade no funcionamento contínuo do relógio. A metodologia prática reforçou o entendimento dos conceitos teóricos envolvidos, além de desenvolver habilidades de diagnóstico e correção de falhas durante a montagem, contribuindo para a formação técnica completa do estudante.

## 4. DESENVOLVIMENTO TEÓRICO

### 4.1 Fonte Retificadora

A fonte retificadora desenvolvida para o projeto do relógio digital teve como objetivo principal fornecer uma tensão contínua estável de aproximadamente 5 V, adequada para a operação dos circuitos digitais. O circuito foi projetado em etapas, começando pela conversão da tensão alternada da rede elétrica. Utilizou-se um transformador com entrada de 127 V e saída de 12 V AC, responsável por reduzir a tensão da rede elétrica para um nível seguro e compatível com os circuitos eletrônicos subsequentes. Em seguida, quatro diodos retificadores foram dispostos em configuração de ponte de Graetz, permitindo a retificação de onda completa — ou seja, a conversão de ambos os semiciclos da corrente alternada em pulsos unidirecionais, aumentando a eficiência energética do sistema.

A saída da ponte retificadora foi conectada a um capacitor eletrolítico de 220 μF com tensão de trabalho entre 35 V e 50 V, que teve a função de filtrar a tensão retificada, reduzindo significativamente as ondulações (ripple) e armazenando carga para fornecer uma tensão mais contínua aos demais componentes. Para estabilizar ainda mais a tensão de saída e proteger os circuitos sensíveis, foi incorporado um circuito regulador com transistor e diodo Zener. O transistor BD135, do tipo NPN, foi utilizado como elemento de amplificação de corrente e chaveamento, atuando como um regulador linear. Sua base foi polarizada por meio de um divisor de tensão formado por um resistor de 1 kΩ e o diodo Zener 1N4734A, com tensão de ruptura de aproximadamente 5,6 V. Esse Zener manteve a tensão constante na base do transistor, permitindo que a tensão de saída do emissor fosse regulada em torno de 5 V, adequada para os circuitos lógicos TTL e CMOS utilizados no projeto.

O resistor de 1 kΩ teve como função limitar a corrente que circula pelo diodo Zener, protegendo-o contra sobrecorrente e garantindo seu funcionamento na região de avalanche controlada. Dessa forma, o conjunto RC, transistor e Zener formou um regulador simples, porém eficiente, capaz de fornecer uma tensão contínua estabilizada com corrente suficiente para alimentar os flip-flops, decodificadores, displays e demais elementos digitais do relógio. A correta escolha e dimensionamento desses componentes foram essenciais para garantir a confiabilidade do sistema e evitar falhas decorrentes de variações na alimentação.

### 4.2 Conversor Analógico-Digital (ADC)

Teoria do funcionamento de conversores ADC.

Aplicação em sistemas digitais.

### 4.3 Circuito de Atraso de Onda

Conceito de atraso de sinal.

Importância no controle de tempo e sincronismo do relógio.

### 4.4 Contadores e Registradores

A contagem de tempo no relógio digital foi realizada por meio de um sistema sequencial composto por flip-flops JK interligados, formando contadores síncronos e assíncronos responsáveis por contabilizar segundos, minutos e horas. O clock principal que alimenta o primeiro flip-flop do sistema foi configurado para operar com um período de 500 ms, correspondente a uma frequência de 2 Hz, garantindo que dois pulsos completos representem exatamente um segundo — permitindo assim a contagem exata de tempo com base em pulsos digitais. Cada unidade de contagem foi construída com flip-flops conectados de forma que a saída <span class="math-inline">Q</span> de um estágio alimenta a entrada de clock do próximo, resultando em uma contagem binária crescente a cada pulso.

Esses agrupamentos de flip-flops funcionam como registradores de 4 bits, representando os dígitos em binário, que posteriormente são decodificados para exibição. Para controlar a transição entre os segmentos (unidade para dezena de segundos, minutos e horas), ao final de cada registrador foi inserida uma porta lógica AND. Essa porta é configurada para detectar quando o conteúdo binário do registrador atinge seu valor máximo programado (como 1001 para contagem até 9, ou 0101 para contagem até 5, conforme o caso). Quando essa condição é satisfeita, a saída da porta AND gera um pulso lógico alto (nível 1), utilizado para duas funções principais: primeiramente, esse pulso é conectado à entrada de clock do primeiro flip-flop do registrador seguinte, promovendo o incremento da próxima casa decimal do relógio (por exemplo, da unidade para a dezena de segundos); em segundo lugar, o mesmo sinal atua no circuito de reset dos flip-flops do registrador correspondente, forçando-os a retornar ao estado lógico 0 e reiniciar a contagem.

Esse sistema de contadores e lógica de controle garante que a contagem seja contínua, sincronizada e compatível com a estrutura decimal exibida nos displays de 7 segmentos. A utilização de portas AND como detectores de estado máximo e geradores de pulso de avanço permitiu eliminar a necessidade de elementos programáveis, mantendo toda a lógica baseada em componentes discretos e lógica combinacional.

## 5. DESENVOLVIMENTO PRÁTICO

### 5.1 Fonte Retificadora

Montagem do circuito retificador.

Testes de tensão e filtragem.

### 5.2 Conversor Analógico-Digital

Implementação do ADC no circuito.

Verificação da conversão de sinal.

### 5.3 Circuito de Atraso de Onda

Montagem prática do circuito de atraso.

Avaliação da estabilidade do tempo.

### 5.4 Contadores e Registradores

Implementação dos contadores para horas, minutos e segundos.

Integração com os displays de LED.

## 6. CIRCUITOS COMPLEMENTARES

### 6.1 Ajuste de horas do relógio

Para possibilitar o ajuste manual do horário no relógio digital, foi implementado um circuito adicional integrado à lógica sequencial dos contadores, visando permitir o avanço controlado dos registradores responsáveis pelas unidades e dezenas de minutos e horas. O princípio de funcionamento desse circuito se baseia na inserção de um botão momentâneo (push-button) entre a saída da porta AND, que identifica o valor máximo em binário de cada registrador, e a entrada de clock do registrador seguinte. Quando o botão é pressionado, ele fecha temporariamente o circuito, permitindo que um pulso lógico seja transmitido manualmente para o próximo registrador, provocando o incremento de seu valor em uma unidade.

Esse mecanismo de ajuste foi replicado entre cada par de registradores, ou seja, entre minutos-unidade e minutos-dezena, até as horas. Dessa forma, o usuário pode ajustar cada campo individualmente ao pressionar o botão correspondente o número de vezes necessário para alcançar o valor desejado. A lógica da porta AND continua operando normalmente durante o funcionamento automático, mas durante o ajuste, o botão assume o papel de controle do avanço do registrador seguinte, independentemente da contagem sequencial do clock.

Esse método de ajuste manual apresenta simplicidade de implementação e confiabilidade no controle dos registros, evitando a necessidade de circuitos programáveis ou sistemas externos. Além disso, garante que o relógio possa ser configurado com precisão em qualquer instante, mantendo a coerência com o sistema lógico previamente implementado nos contadores.

### 6.2 LEDs de separação de unidades

Para melhorar a visualização e separar visualmente os segmentos de horas, minutos e segundos no display, foi implementado um circuito com LEDs de separação entre cada uma das unidades temporais. Este circuito utiliza um total de quatro LEDs, dispostos de maneira a intercalar os algarismos de horas, minutos e segundos no display de 7 segmentos. Cada par de LEDs, dois em cada separador, foi conectado a uma porta inversora (NOT), com a entrada da porta ligada diretamente ao clock original do sistema — o mesmo clock que alimenta os flip-flops responsáveis pela contagem.

A função dessa configuração é manter os LEDs constantemente acesos durante o funcionamento do relógio, pois a inversora inverte a fase do sinal de clock original. Assim, quando o sinal do clock está ao nível alto, a porta inversora gera um nível baixo na saída, e vice-versa, fazendo com que os LEDs se mantenham sempre iluminados, independentemente do valor contido nos registradores de horas, minutos ou segundos. Isso cria um efeito visual contínuo, destacando claramente a separação entre as unidades temporais, sem interferir no funcionamento da contagem ou na exibição dos valores. O uso da porta inversora, juntamente com o clock original, assegura um controle simples e eficiente para manter os LEDs iluminados durante todo o ciclo de operação do relógio.

### 6.3 Contador de potência da Bateria

O circuito de contador de potência da bateria foi implementado visando fornecer uma indicação visual e intuitiva do nível de carga restante da bateria que alimenta o sistema. Esse indicador é composto por quatro LEDs conectados em paralelo, cada um em série com um resistor de 1 kΩ, formando um arranjo simples e eficiente para monitoramento percentual da tensão da fonte. A alimentação do circuito é feita diretamente a partir dos terminais da bateria, sem a necessidade de circuitos complexos de medição ou microcontroladores.

Cada LED representa uma fração de 25% da carga total da bateria: com os quatro LEDs acesos, o sistema está operando com carga plena (100%); com três LEDs, a carga estimada é de 75%; dois LEDs indicam 50%, e somente um LED aceso representa cerca de 25% da capacidade restante. Quando todos os LEDs estão apagados, assume-se que a bateria está próxima da descarga completa.

A divisão da corrente entre os resistores de 1 kΩ assegura uma limitação adequada da corrente que passa por cada LED, evitando sobrecarga e prolongando a vida útil dos componentes. A associação em paralelo permite que a ativação dos LEDs seja diretamente influenciada pela tensão da bateria: conforme o nível de tensão diminui, a diferença de potencial não é mais suficiente para acionar todos os LEDs, fazendo com que eles se apaguem progressivamente, de acordo com sua posição no circuito. Esse método simples e eficaz proporciona ao usuário uma leitura visual instantânea do estado da alimentação, contribuindo para a manutenção preventiva e garantindo o funcionamento confiável do relógio digital.

## 7. CONCLUSÕES

O desenvolvimento do relógio digital de LED proposto neste projeto permitiu a aplicação prática de diversos conceitos fundamentais da eletrônica digital e analógica, por meio da construção de um circuito totalmente integrado, sem o uso de programação. A estrutura do sistema foi organizada em módulos interdependentes, iniciando pela fonte retificadora, composta por um transformador de 127 V para 12 V, quatro diodos retificadores, um capacitor de 220 µF, um resistor de 1 kΩ, um transistor BD135 e um diodo Zener 1N4734A, que juntos forneceram uma alimentação estabilizada para o circuito.

O núcleo do sistema foi construído com base em flip-flops JK, organizados em registradores e contadores binários que, por meio de ligações entre saídas <span class="math-inline">Q</span> e entradas de clock subsequentes, garantiram a contagem precisa de segundos, minutos e horas. A lógica de controle foi complementada com portas AND, responsáveis por detectar o valor máximo de cada registrador e acionar tanto o reset dos flip-flops quanto o avanço do registrador seguinte. O sinal de clock, operando a 2 Hz (500 ms), foi a base do sincronismo de toda a contagem.

Para garantir interatividade, foi implementado um sistema de ajuste de horas, em que botões inseridos entre as portas AND e os flip-flops permitiram o avanço manual de cada registrador. A visualização do tempo foi organizada com displays de 7 segmentos, separados por LEDs auxiliares controlados por portas inversoras ligadas ao clock, mantendo-os sempre acesos para delimitar claramente as unidades de tempo.

Além disso, foi incorporado um indicador de potência da bateria com quatro LEDs e resistores de 1 kΩ associados em paralelo, permitindo uma leitura visual da carga restante com base na tensão disponível da fonte. Essa solução compacta e prática fornece uma noção clara do status energético do sistema.

Assim, o projeto final unificou conhecimentos em retificação
