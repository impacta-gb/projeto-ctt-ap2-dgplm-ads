---
icon: simple/go
---

# Sintaxe Básica e Variáveis em Go

## Introdução

A linguagem Go (Golang) foi criada com foco em simplicidade, desempenho e concorrência. Sua sintaxe é enxuta e fácil de ler, tornando o desenvolvimento mais rápido e organizado.

---

## Estrutura Básica de um Programa

Exemplo simples de um programa em Go:

```go
package main

import "fmt"

func main() {
    fmt.Println("Olá, Mundo!")
}
```

### Explicação

| Elemento        | Função                                   |
| --------------- | ---------------------------------------- |
| `package main`  | Define o pacote principal do programa    |
| `import`        | Importa bibliotecas                      |
| `func main()`   | Função principal executada pelo programa |
| `fmt.Println()` | Exibe texto no terminal                  |

---

## Declaração de Variáveis

Em Go, variáveis podem ser declaradas utilizando `var`.

```go
var nome string = "Diego"
var idade int = 20
```

---

## Inferência de Tipo

Go consegue identificar automaticamente o tipo da variável.

```go
var cidade = "São Paulo"
```

---

## Declaração Curta

A forma mais utilizada é a declaração curta com `:=`.

```go
nome := "Carlos"
idade := 25
```

> [!NOTE]
> O operador `:=` só pode ser utilizado dentro de funções.

---

## Tipos Básicos

| Tipo      | Descrição           |
| --------- | ------------------- |
| `int`     | Números inteiros    |
| `float64` | Números decimais    |
| `string`  | Texto               |
| `bool`    | Verdadeiro ou falso |

---

## Exemplo Completo

```go
package main

import "fmt"

func main() {

    nome := "Maria"
    idade := 30
    altura := 1.68
    estudante := true

    fmt.Println(nome)
    fmt.Println(idade)
    fmt.Println(altura)
    fmt.Println(estudante)
}
```

---

## Constantes

Constantes utilizam a palavra-chave `const`.

```go
const PI = 3.14
```

---

## Comentários

Comentários em linha:

```go
// Comentário simples
```

Comentários em bloco:

```go
/*
Comentário
de múltiplas linhas
*/
```

---

## Boas Práticas

> [!TIP]
> Utilize nomes claros e objetivos para variáveis.

> [!WARNING]
> Evite variáveis globais desnecessárias.

---

## Conclusão

A sintaxe simples do Go facilita a manutenção do código e melhora a produtividade dos desenvolvedores. O sistema de tipos é seguro e eficiente, tornando a linguagem ideal para aplicações modernas e escaláveis.
