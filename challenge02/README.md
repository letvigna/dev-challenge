# Desafio 02 (12/05/2022):

Dado essa estrutura de dados do tipo Person:

```
type Person {
  ID string
  Friends []string
}

var people []Person

people = []Person {
  Person{ID: "0", Friends: []string{"4", "1"}},
  Person{ID: "1", Friends: []string{"2", "3"}},
  Person{ID: "2", Friends: []string{"1"}},
  Person{ID: "3", Friends: []string{"2", "4"}},
  Person{ID: "4", Friends: []string{"3"}},
}
```

Escreva um algoritmo que dado um ID, retorne três Arrays:

1 - Array dos amigos (chave Friends).

2 - Array dos amigos dos amigos(utilizando os valores no array 1, pegue os amigos de cada ID).

3 - Array dos amigos dos amigos dos amigos do dev (utilizando os valores no array 2, pegue os amigos de cada ID).

Não esqueça de remover duplicatas, então se no array 2, existir o ID "1" mais de uma vez, ele não deve ser repetido nesse array, porém, ele pode aparecer em outros arrays.

## Exemplo

Input: `GetSocialBubbles(people, "0")`

Output:

```
[4 1]
[3 2]
[2 4 1]
```
