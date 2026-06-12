# Projeto Computabilidade Tradutor Morse de mutiplas fitas
# Tradutor de Código Morse utilizando Máquina de Turing de Fita Dupla

## Informações Gerais

**Disciplina:** Teoria da Computabilidade

**Turma:** cc5ma e cc5na respectivamente

**Professor:** Daniel Alves

**Integrantes:**

* Vitor Hugo Santos
* Caiky de morais alves

---

# Descrição do Projeto

Este projeto consiste na implementação de uma Máquina de Turing de Fita Dupla desenvolvida na ferramenta JFLAP para realizar a tradução de código Morse para letras do alfabeto.

A máquina recebe na Fita 1 uma sequência composta pelos símbolos:

* `.` (ponto)
* `-` (traço)
* ` ` (espaço)

Cada sequência de pontos e traços representa uma letra em código Morse. Os espaços são utilizados para indicar a separação entre letras.

A Máquina de Turing percorre uma árvore de decisão equivalente à árvore do código Morse, utilizando seus estados para representar cada possível caminho até identificar a letra correspondente.

Após identificar uma letra, ela é escrita na Fita 2 e a máquina vai ao estado Estado auxiliar para processar a próxima sequência Morse. 

Se houver uma sequencia de 2 espaços, a maquina interpreta como o fim de uma palavra e o começo de outra

Quando ele encontra uma entrada vazia na fita 1 e 2, o programa registra a ultima letra no estado que ele esta e encerra o programa
---

# Modelo Escolhido

**Tipo de Máquina:**

* Máquina de Turing Multifaixa (2 fitas)
* Implementada no JFLAP

**Quantidade de Estados:** 29

**Estado Inicial:** q0

**Estado Final:** q28

---

# Definição Formal

A máquina é definida pela 7-tupla:

M = (Q, Σ, Γ, δ, q0, B, F)

## Conjunto de Estados

Q = {q0, q1, q2, q3, q4, q5, q6, q7, q8, q9, q10, q11, q12, q13, q14, q15, q16, q17, q18, q19, q20, q21, q22, q23, q24, q25, q26, q27, q28}

### Significado dos Estados

| Estado | Representação |


| q0  | Inicial |

| q1   E |

| q2  | T |

| q3  | I |

| q4  | A |

| q5  | S |

| q6  | U |

| q7  | R |

| q8  | W |

| q9  | N |

| q10 | M |

| q11 | D |

| q12 | K |

| q13 | G |

| q14 | O |

| q15 | H |

| q16 | V |

| q17 | F |

| q18 | L |

| q19 | P |

| q20 | J |

| q21 | B |

| q22 | X |

| q23 | C |

| q24 | Y |

| q25 | Q |

| q26 | Z |

| q27 | Estado Auxiliar |

| q28 | Final |

---

## Alfabeto de Entrada

Σ = { ., -, espaço }

---

## Alfabeto da Fita

Γ = { ., -, espaço, A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z, □ }

Onde:

* `□` representa o símbolo vazio (blank)
* `espaço` representa o separador entre letras em código Morse

---

## Estado Inicial

q0

---

## Símbolo Branco

B = □

---

## Estados Finais

F = { q28 }

---

# Problema Resolvido

A máquina resolve o problema da tradução de mensagens escritas em código Morse para texto alfabético.

A entrada consiste em uma sequência de pontos e traços, em que letras são separadas por 1 espaço e palavras por 2.

A saída consiste na palavra ou frase decodificada

Exemplo:

Código Morse:

.... . .-.. .-.. ---

Saída:

HELLO

---

# Funcionamento

1. A máquina inicia no estado q0.
2. Lê o primeiro símbolo da Fita 1.
3. Dependendo do símbolo (`.` ou `-`), percorre a árvore Morse através dos estados.
4. Ao identificar uma letra:

   * escreve a letra correspondente na Fita 2;
   * Vai para o estado.
5. Quando encontra um espaço:

   * considera que a letra terminou;
   * inicia a leitura da próxima sequência Morse.

6. Quando encontra 2 espaços:

   * considera que a palavra terminou;
   * inicia a leitura da próxima sequência Morse.

6. Ao atingir o fim da entrada(ele detecta o final como a fita 1 vazia), realiza a transição para q28 e encerra a execução, pritando a ultima letra dependendo de qual estado estava..

---

# Dependências

Para executar este projeto é necessário:

* Java Runtime Environment (JRE) 8 ou superior
* JFLAP 7.1 ou versão compatível

Download do JFLAP:

https://www.jflap.org

---

# Instruções de Execução

1. Abrir o JFLAP.

2. Selecionar **File → Open**.

3. Abrir o arquivo:

   `MaquinaMultiFitaCodigoMorse.jff`

4. Selecionar:

   Input → Fast Run

   ou

   Input → Step

5. Informar uma sequência Morse válida na Fita 1.

6. Executar a máquina.

7. Observar a tradução produzida na Fita 2.

---

# Exemplos de Uso

## Exemplo 1

Entrada:

....

Saída:

h

---

## Exemplo 2

Entrada:

.-

Saída:

a

---

## Exemplo 3

Entrada:

.... . .-.. .-.. ---

Saída:

hello


---

## Exemplo 4

Entrada:

.- -... -.-. -.. . ..-. --. .... .. .--- -.- .-.. -- -. --- .--. --.- .-. ... - ..- ...- .-- -..- -.-- --..

Saída:

abcdefghijklmnopqrstuvwxyz

---

## Exemplo 5

Entrada:

--.. . -... .-. .- ...  -.-. .- --- .-.. .... .- ...  -.. .  .--- .- ...- .-  --.- ..- . .-. . --  -- .- -. -.. .- .-.  ..-. .- -..-  .--. .- .-. .-  -- --- .-  --. .. --. .- -. - .  -.. .  -. . .--  -.-- --- .-. -.-

Saída:

zebras caolhas de java querem mandar fax para moca gigante de new york

---

# Arquivos Entregues

* README.md
* MaquinaMultiFitaCodigoMorse.jff
* 

---

# USO DE IA

Eu, Vitor Hugo, usei o CHAT GPT para:
-Auxilio Didatico
-Correção de Bugs
-A Parte da definição formal do programa
-Geração da base desse readme.md
