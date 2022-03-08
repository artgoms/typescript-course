# Tipar Objetos!



### Intefaces

```typescript
type UF = 'PE' | 'SP' | 'MG'

interface User {
     name: string,
     address: {
         city:string,
         UF: UF
     }
}

function showCity(user: User) {
	return user.address.city
}
```



### Propriedades Opcionais

 Falando para o typescript que uma propriedade é opcional. No caso, colocando um '?' ao final da propriedade

```typescript
type UF = 'PE' | 'SP' | 'MG'

interface User {
     name: string,
     address?: {
         city:string,
         UF: UF
     }
}

function showCity(user: User) {
	return user.address?.city //  return user.address ? user.address.city : 'não existe bb'
}
```

### Propriedades ReadyOnly

A propriedade readyonly faz com que não seja possível modificar a string, number etc.

```typescript
interface User {
    readonly name: string,
    age: number
}

let user: User {
    name: 'Artur Gomes',
    age: 30,
}

user.age = 31
user.name = 'João Gomes'
```

### Extends  & Implements 

Extends é quando queremos unir duas Interfaces e Implements serve para criar uma classe a partir de uma Interface.



Exemplo de Extends:

Extender as tipagens do Veículo para Moto.

```typescript
interface Veiculo {
    rodas: number
    acelerar: () => void
    frear: () = void
}
    
inteface Moto extends Veiculo {
    capacete: boolean
    empinar: () => void
}
    
let bross: Moto

bross.acelerar
```

Exemplo de Implements:

```typescript
interface Veiculo {
    rodas: number
    acelerar: () => void
    frear: () = void
}
    
class CriarVeiculo implements Veiculo{
    rodas: number
    
    constructor(rodas: number) {
        this.rodas = rodas
    }
}
```

### Pick & Omit

Pick selecionar algumas propriedades de uma interface ou tipo, e com base nessas, criar um novo tipo.

Omit faz ao contrário, omite algumas propriedades.

Exemplo para o Pick

```typescript
 interface Post {
     id: number
     title: string
     description: string
 }

type PostPreview = Pick<Post, 'id' | 'title'>

let post: PostPreview

post.description

```

Exemplo para o Omit:

```typescript
 interface Post {
     id: number
     title: string
     description: string
 }

type PostPreview = Omit<Post, 'id' | 'title'>

let post: PostPreview

post.description

```













