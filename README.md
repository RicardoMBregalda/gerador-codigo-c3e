# Gera Código – Soma e Multiplicação (C3E)

Este projeto implementa um **analisador léxico e sintático** em C que, a partir de um código-fonte simples em C (`teste.c`), gera código intermediário (estilo *three-address code* ou *C3E*).  

O objetivo é reconhecer estruturas básicas da linguagem (expressões aritméticas, relacionais e comandos de controle como `if`, `while` e `for`) e produzir uma saída intermediária (`saida.kvmp`) que pode ser usada para fins de estudo de compiladores.

---

## 📌 Funcionalidades

- **Analisador léxico**:
  - Reconhecimento de identificadores, constantes inteiras, operadores aritméticos e relacionais.
  - Tratamento de palavras reservadas (`int`, `float`, `if`, `else`, `while`, `for`, etc.).

- **Analisador sintático com geração de código**:
  - Expressões aritméticas (`+`, `-`, `*`).
  - Expressões relacionais (`>`, `<`, `>=`, `<=`, `==`, `!=`).
  - Comandos de atribuição.
  - Estruturas de controle:
    - `if` / `else`
    - `while`
    - `for`
    - Blocos compostos (`{ ... }`)
    - `continue` e `break`.

- **Geração de código intermediário**:
  - Uso de variáveis temporárias (`T001`, `T002`, ...).
  - Uso de rótulos (`LB001`, `LB002`, ...) para saltos condicionais e laços.
  - Código final escrito em formato textual no arquivo `saida.kvmp`.

---

## 📂 Estrutura

- `gera_codigo_soma_mult_C3E.cpp` → Arquivo principal com todo o código do analisador e gerador.
- `teste.c` → Arquivo de entrada contendo o código-fonte a ser analisado (deve ser criado pelo usuário).
- `saida.kvmp` → Arquivo de saída com o código intermediário gerado.

---

## ▶️ Como Compilar e Executar

### 🔹 Compilar
```bash
gcc gera_codigo_soma_mult_C3E.cpp -o gera_codigo
```

> ⚠️ Observação: o código usa `<conio.h>`, que pode não estar disponível em sistemas Unix/Linux. Caso dê erro, você pode remover a dependência ou substituir a função `getch()`.

### 🔹 Executar
```bash
./gera_codigo
```

- O programa espera encontrar o arquivo `teste.c` no mesmo diretório.
- Após a execução, o código intermediário será impresso no console e gravado em `saida.kvmp`.

---

## 📖 Exemplo

Entrada (`teste.c`):
```c
int a;
a = 3 + 5 * 2;
```

Saída (`saida.kvmp`):
```asm
    T001 = 3
    T002 = 5
    T003 = 2
    T004 = T002 * T003
    T005 = T001 + T004
    a = T005
```

---

## 🚀 Próximos Passos (sugestões de melhoria)

- Suporte a **expressões booleanas mais complexas**.
- Tratamento de **tipos além de inteiros** (`float`, `char`).
- Implementação de **funções** e **escopos locais**.
- Melhoria na geração de código para facilitar posterior compilação para assembly real.

---

## 👨‍💻 Autor
Projeto desenvolvido para estudo de **compiladores** e geração de código intermediário.
