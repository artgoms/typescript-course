## String

String é tudo aquilo que está entre aspas, duplas, simples ou crases.

```typescript
let message: string = 'Hello World';

console.log(message) // Hello World
```



## Number

Todo tipo de número, não importa se seja fracionado ou não. Só não pode estar entre aspas ou crases.

```typescript
let total: number

total = 0;
```



## Boolean

Aceita somente verdadeiro e falso.

```typescript
let isOpen: boolean

isOpen = false
```

## Any

O tipo any aceita qualquer coisa, seja string, número, null, objeto, etc. *Entretanto, não é legal utilizar o tipo any, pois irá tirar o propósito da tipagem estática do Typescript.*

A utilização do any seria quando estiver construindo um protótipo, por exemplo, e quiser acelerar o processo, ou quando instala um pacote que não possui definição de tipos.

Propósito do typescript = evitar erros no desenvolvimento.

Exemplo:

Temos uma loja e temos um stock nulo, o typescript já alerta.

```typescript
let stock: number = 89;

stock = null // typescript alerta null como não assinável ao tipo number

```

Usando o tipo any o typescript aceita qualquer coisa.

```typescript
let stock: any = 89;

stock = true;

```

## Void

Da tradução "vazio". Único valor capaz de satisfazer esse tipo é o undefined (o que não faz o menor sentido). Vazio seria o valor null, não undefined ~ mas o typescript reclama 😒.

É utilizado, marjoritariamente para tipar o retorno de uma função que não retorna nada.

Exemplo:

Retornando string, número, etc, uma função poderia ser escrita dessa maneira

```typescript
function showInformation(): string {
    return 'oi bb'
}
```

Não tendo um retorno, seria escrita assim:

```typescript
function showInformation(): void {
    console.log('oi bb') // aqui nós executamos uma ação, não retornando nada.
}

```

## Never

O tipo never não aceita nenhum tipo, sendo principalmente usado pra tipar funções que tem loop infinito ou exceções (poderia ser um erro).

Exemplo:

```typescript
function error(): never {
    throw new Error('error')
}
```

Não tendo um retorno, seria escrita assim:

```typescript
function showInformation(): void {
    console.log('oi bb') // aqui nós executamos uma ação, não retornando nada.
}
```

## Array

Array pode ser escrita de diversas formas, como:

Array<number> 

number[]

```typescript
let items: string[]
    
items = [1,2,3,4,5]
```

## Tuple

Uma array que já sabemos seu comprimento (quantidade de itens) e tipo de cada um.

```typescript
let items: [number, string, boolean]
    
items = [1, 'oi bb', true] // ele só aceita dessa forma.
```

## Enum

De enumerador, ele serve para criar um conjunto de chaves e valores.

```typescript
enum Colors {
    white = '#fff',
    black = '#000'
}

let white: Colors = Colors.white
```

## Type Union

União de tipo, aceita mais de um tipo.

exemplo 1:

```typescript
let age: number | string

age = 20

age = 'vinte'
```

exemplo 2:

```typescript
function showPet(pet: 'dog' | 'cat' | 'zebra') {
    console.log(pet)
}

showPet('cat')
```

## Type Aliases

Seria traduzido para Apelido de Tipo, o que faz não precisar repetir coisas

```typescript
type Pet = 'dog', 'cat', 'zebra'

function showPet(pet: Pet) {
    console.log(pet)
}

function displayPet(pet: Pet) {
    console.log(pet)
}

showPet('cat')
displayPet('cat')
```

## Type Inference

Inferencia de Tipo. O typescript é inteligente o suficiente para entender se algo é número, string etc. Então fica redundante declarar e escrever que algo é string como no exemplo abaixo.

Somente em situações em que o typescript não consegue definir o tipo, devemos definir.

```typescript
let message: string = 'oi bb'
```

Exemplo

```typescript
window.addEventListener('click', (event: MouseEvent) =>{
    console.log(event.target) // o typescript já identificou que é um MouseEvent, não necessitando colocar o que é na frente do event no inicio da função.
})
```

## Type Assertion

Afirmação de tipos. Em situações que temos a 

Exemplo:

Nessa situação temos uma consulta(query) que pode falhar, então podemos ter um possível vazio.

```typescript
const inputName = document.querySelector('#name') as HTMLInputElement

inputName.value
```

