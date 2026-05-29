---
icon: simple/go
---

# Concorrência I: Goroutines

## O que são Goroutines?

Goroutines são funções executadas concorrentemente em Go.

Elas permitem executar múltiplas tarefas ao mesmo tempo de forma leve e eficiente.

---

## Criando uma Goroutine

Para transformar uma função em goroutine, utilize a palavra-chave `go`.

```go
package main

import (
    "fmt"
    "time"
)

func mensagem() {
    fmt.Println("Executando Goroutine")
}

func main() {
    go mensagem()

    time.Sleep(time.Second)
}
```

!!! note
    O programa principal pode finalizar antes da goroutine executar.

---

## Executando múltiplas Goroutines

```go
package main

import (
    "fmt"
    "time"
)

func tarefa(nome string) {
    for i := 1; i <= 3; i++ {
        fmt.Println(nome, i)
        time.Sleep(time.Millisecond * 500)
    }
}

func main() {
    go tarefa("Goroutine 1")
    go tarefa("Goroutine 2")

    time.Sleep(time.Second * 3)
}
```

!!! warning
    Goroutines sem controle podem causar concorrência desorganizada.

---

## Vantagens das Goroutines

| Vantagem | Descrição |
|---|---|
| Leves | Consomem pouca memória |
| Concorrentes | Executam tarefas simultaneamente |
| Escaláveis | Suportam milhares de execuções |

---

## Conclusão

Goroutines são um dos recursos mais poderosos da linguagem Go para processamento concorrente.