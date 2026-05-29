# Tratamento de Erros (Error Handling)

Go aborda o tratamento de erros de uma forma diferente da maioria das linguagens. Não existem blocos `try/catch` ou exceções tradicionais. Erros são tratados como valores normais de retorno.

## O tipo `error`

Em Go, `error` é uma interface embutida. Uma função que pode falhar geralmente retorna o resultado esperado e um erro como o último valor de retorno.

> **Aviso:** Sempre verifique se o erro retornado é diferente de `nil` antes de prosseguir com a lógica do seu código. Ignorar erros é considerado uma péssima prática em Go.

## Exemplo Prático

Abaixo, um exemplo de como verificar erros ao tentar converter uma string para um número inteiro usando o pacote `strconv`.

```go
package main

import (
    "fmt"
    "strconv"
)

func main() {
    numeroTexto := "100"
    
    // A função Atoi retorna o número convertido e um possível erro
    numero, err := strconv.Atoi(numeroTexto)
    
    if err != nil {
        fmt.Println("Falha ao converter:", err)
        return
    }
    
    fmt.Printf("A conversão foi um sucesso! O número é %d\n", numero)
}
´´´
## Criando seus próprios erros
Você pode gerar erros customizados facilmente utilizando o pacote errors.
´´´go
package main

import (
    "errors"
    "fmt"
)

func dividir(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("impossível dividir por zero")
    }
    return a / b, nil
}
´´´