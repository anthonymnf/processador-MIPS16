# MIPS 16-bit Processor

Este projeto consiste na implementação de um processador MIPS de 16 bits, desenvolvido como parte da avaliação da disciplina **Sistemas Digitais Embarcados**. O processador foi projetado para executar instruções básicas do conjunto de instruções MIPS, suportando diferentes tipos de operações, como aritméticas, lógicas, de memória e de controle de fluxo.

## Arquitetura

O processador implementa uma arquitetura de 16 bits com os seguintes componentes principais:

- **Banco de Registradores**: Possui 8 registradores de 16 bits, onde cada registrador pode ser acessado através de um endereço de 3 bits.
- **ALU (Arithmetic Logic Unit)**: Capaz de realizar operações aritméticas e lógicas, incluindo adição, subtração, XOR, AND, OR e outras operações.
- **Memória de Instruções**: Armazena as instruções do programa a serem executadas.
- **Memória de Dados**: Utilizada para carregar e armazenar dados, operando com as instruções do tipo Load Word (LW) e Store Word (SW).
- **Controle**: Unidade de controle responsável por decodificar as instruções e gerar os sinais de controle adequados para cada operação.

### Formato das Instruções

As instruções seguem o seguinte formato de 16 bits, dividido em três tipos principais:

- **R-type (Operações Aritméticas e Lógicas)**:
  - 3 bits para o opcode
  - 3 bits para o registrador fonte 1 (rs)
  - 3 bits para o registrador fonte 2 (rt)
  - 3 bits para o registrador destino (rd)
  - 4 bits para a função (funct), especificando a operação a ser realizada pela ALU
- **I-type (Instruções de Memória e Desvios)**:

  - 3 bits para o opcode
  - 3 bits para o registrador fonte (rs)
  - 3 bits para o registrador alvo (rt)
  - 7 bits para o endereço ou imediato (address/imm)

- **J-type (Instruções de Desvio Incondicional - Jump)**:
  - 3 bits para o opcode
  - 13 bits para o endereço de destino (target address)

### Instruções Suportadas

- **Instruções Aritméticas e Lógicas (Tipo R)**:
  - ADD, SUB, AND, OR, XOR.
- **Instruções de Memória (Tipo I)**:
  - **LW (Load Word)**: Carrega uma palavra de 16 bits da memória para um registrador.
  - **SW (Store Word)**: Armazena uma palavra de 16 bits de um registrador na memória.
- **Instruções de Controle de Fluxo (Tipo I e J)**:
  - **JUMP (Tipo J)**: Desvia incondicionalmente para um endereço especificado.

### Funcionalidade do Campo Funct (Instruções R-type)

O campo `funct` de 4 bits nas instruções do tipo R especifica qual operação a ALU deve executar. Com 4 bits, é possível codificar até 16 operações diferentes. Isso permite que o processador realize uma ampla variedade de operações aritméticas e lógicas.

## Funcionamento das Instruções de Memória

- **LW (Load Word)**: Carrega um valor da memória para um registrador. O endereço de memória é calculado somando o valor do registrador base (rs) com um deslocamento imediato.
- **SW (Store Word)**: Armazena o valor de um registrador em um endereço de memória. O endereço é calculado de forma semelhante à instrução LW.

## Controle

O controle do processador foi implementado de forma a decodificar os campos `opcode` e `funct`, gerando os sinais de controle para a ALU, banco de registradores, memória, e outros componentes.

## Simulação e Testes

O processador foi simulado usando Verilog, e as principais instruções foram testadas em diferentes cenários para garantir o funcionamento correto. Testes foram realizados com operações aritméticas, lógicas, manipulação de memória e controle de fluxo.

## Conclusão

Este projeto proporcionou uma compreensão mais profunda sobre a construção de processadores e o funcionamento interno de arquiteturas MIPS. A implementação deste processador de 16 bits demonstrou os principais conceitos de sistemas embarcados, arquitetura de processadores e projeto em Verilog.

---

### Desenvolvido por:

**Anthony Matheus**
