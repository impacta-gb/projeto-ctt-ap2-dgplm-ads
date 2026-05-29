# Estruturas de Controle em Go

A linguagem Go possui um conjunto enxuto e poderoso de estruturas de controle de fluxo. Diferente de outras linguagens, Go não utiliza parênteses ao redor das condições.

## If / Else

A estrutura `if` em Go é simples e permite a declaração de uma variável de escopo curto antes da condição.

```go
package main

import "fmt"

func main() {
    // Exemplo básico
    idade := 18
    if idade >= 18 {
        fmt.Println("Maior de idade")
    } else {
        fmt.Println("Menor de idade")
    }

    // Com declaração de variável
    if x := 10; x > 5 {
        fmt.Println("x é maior que 5")
    }
}
```
>Aviso: Variáveis declaradas na condição do if só existem dentro do escopo daquele bloco if e de seus respectivos else.
##For (O único laço de repetição)
Go não possui while ou do-while. O for é utilizado para todos os cenários de laço de repetição.
```go
package main

import "fmt"

func main() {
    // Estilo tradicional (como no C)
    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }

    // Estilo "while"
    soma := 1
    for soma < 100 {
        soma += soma
    }
}
```
##Switch
O switch em Go é mais seguro do que no C ou Java, pois ele quebra o fluxo automaticamente (não exige a palavra break no final de cada caso).

```go
package main

import (
    "fmt"
    "time"
)

func main() {
    hoje := time.Now().Weekday()

    switch hoje {
    case time.Saturday, time.Sunday:
        fmt.Println("Fim de semana!")
    default:
        fmt.Println("Dia útil.")
    }
}

```