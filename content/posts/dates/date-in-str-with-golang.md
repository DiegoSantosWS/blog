+++
title = "Convertendo datas em string usando Golang"
date = 2021-06-30T16:12:06-03:00
draft = false
toc = true
images = ""
slug = "date/"
tags = ["date","convert at string"]

+++

Neste post vou mostrar como converter data em string.

Em Go isso é muito simples, pois já foi pensado para ser simples.

Veja um exemplo, onde usaremos o pacote **time** da própria linguagem para trabalhar a data atual.

```go

import (
    "time"
    "fmt"
)

func main() {
    now := time.Now()
}
```

A variável **now** recebe o valor de `time.Now`, mas ainda temos um valor do tipo `time.Time`. O código assim se executado vai gerar um erro, por que não podemos declarar uma variável e não usa-lá.



No exemplo anterios nó so declaramos a variável que iremos usar, no exemplo à seguir veja como se usa.

```go

func main() {
  now := time.Now()
  dateStr := now.Format("2006-01-02")
  fmt.Println("Data atual é:", dateStr)
}

// ~$ Data atual é: 2021-06-30
```

Ah mas por que você usou a variaval **now**?

Bom como `time` é um pacote ele tem uma série de funções públicas e uma delas é **Format**, função recebe um parâmetro, no formato de uma data, na minha opinião é "locura" mas já acostumei e decorei kkkkkk, é com esse parâmetro que definimos o formato que a data será exposta na tela ou terminal. Como é feito no exemplo acima.

Ainda usando a função **Format** vamos mostrar a data e hora atual, que também é bem simples, basta add a hora **15:04:02** logo após a data.

```go
func main() {
  now := time.Now()
  dateHoraStr := now.Format("2006-01-02 15:02:04")
  
  fmt.Println("Data atual é:", dateHoraStr)
}

// ~$ Data e hora atual é: 2021-06-30 10:05:00
```

É isso pessoal.

Para ver os exemplo usados neste artigo acesse: [string.go](https://github.com/DiegoSantosWS/godate/blob/master/datetostring/string.go)
