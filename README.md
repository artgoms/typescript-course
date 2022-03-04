# O que é Typescript?

É uma linguagem de programação criada pela Microsoft.

Javascript e Typescript não são a mesma coisa, são desacopladas e mantidas por empresas diferentes.

Typescript é um SUPERSET totalmente baseada no Javascript.

Typescript é uma Tipagem ESTÁTICA, enquanto o Javascript é uma Tipagem DINÂMICA.

<u>exemplo:</u>

```javascript
// Javascript - Tipagem dinâmica

let name = 'Artur Gomes'
console.log(name) // Artur Gomes

name = 12345
console.log(name) // 12345
```

Nesse exemplo, a variável name pode armazenar valores independente do seu tipo.



```typescript
// Typescript - Tipagem estática

let name: string = 'Artur Gomes'
console.log(name) // Artur Gomes

name = 12345 // Type 'number' is not assignable to type 'string'.
console.log(name) // 12345
```

Nesse exemplo, temos que definir no inicio que tipo e então armazenar o valor.

Ao mudar o valor, o typescript irá avisar que o name está tipado como string, não como number.

# Por quê usar o Typescript??

*VANTAGENS* 👌👌

O principal motivo para utilizar o Typescript é para evitar erros inesperados, <u>criando um código mais seguro</u>, reduzindo também diversos testes unitários.

Também, o uso do Typescript funciona como uma espécie de documentação em momento de desenvolvimento, evitando que precise <u>**decorar coisas e facilitando a manutenção e trabalho em equipe.**</u>

ANDD MORE!

Acesso aos últimos recursos do Javascript, como Type copila Javascript, sempre estará atualizado com a última feature.

Fornece mais escalabilidade e manutenibilidade.

**Uso opcional!**

*DESVANTAGENS* 👎

Necessidade de compilação.

Diminui a produtividade **no início**.



exemplo:

```javascript
// Função que realiza a soma de dois números com Javascript

function sum(a, b) {
    return a + b
}

sum(1, 2) // 3
sum('1', '2') // 12 
```

O Javascript faz uma cocatenação, não uma soma.



```typescript
// Função que realiza a soma de dois números com Typescript

function sum(a:number, b:number) {
    return a + b
}

sum('1', '2') //  " Argument of type 'string' is not assignable to parameter of type 'number' "

```

O Typescript já emite um erro dizendo que tem que ser do tipo number.

