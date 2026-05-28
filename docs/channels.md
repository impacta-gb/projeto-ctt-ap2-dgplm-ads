---
icon: simple/go
---

# Concorrência II: Channels

## O que são Channels?

Channels permitem comunicação segura entre goroutines.

Eles são utilizados para enviar e receber dados.

---

## Criando um Channel

```go
package main

import "fmt"

func main() {
    canal := make(chan string)

    go func() {
        canal <- "Olá Channel"
    }()

    mensagem := <-canal

    fmt.Println(mensagem)
}
```

!!! tip
    Channels ajudam a evitar problemas de concorrência.

---

## Enviando e recebendo dados

| Operação | Sintaxe |
|---|---|
| Enviar | `canal <- valor` |
| Receber | `valor := <-canal` |

---

## Exemplo com múltiplas mensagens

```go
package main

import "fmt"

func main() {
    numeros := make(chan int)

    go func() {
        for i := 1; i <= 5; i++ {
            numeros <- i
        }

        close(numeros)
    }()

    for numero := range numeros {
        fmt.Println(numero)
    }
}
```

!!! warning
    Um channel fechado não pode receber novos valores.

---

## Tipos de Channels

| Tipo | Função |
|---|---|
| Bidirecional | Envia e recebe |
| Somente envio | Apenas envia |
| Somente leitura | Apenas recebe |

---

## Conclusão

Channels são fundamentais para sincronização e troca de informações entre goroutines em Go.