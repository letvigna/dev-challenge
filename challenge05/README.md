# Desafio 05 (13/06/2022):

Nesse desafio nós vamos trabalhar com árvores, mais precisamente árvore binária de busca. Resumindo muito, uma árvore binária de busca, é uma estrutura de dados que se organiza de tal forma que quando você precisa inserir um elemento, caso ele tenha um valor menor que o atual, ele será inserido para esquerda, caso contrário, será inserido para direita.

Você pode entender melhor com as seguintes referências:

- https://www.youtube.com/watch?v=VmKkAQtnjsM&ab_channel=Programa%C3%A7%C3%A3oDin%C3%A2mica
- https://en.wikipedia.org/wiki/Binary_search_tree
- https://medium.com/arctouch/data-structure-101-part-4-57c19ec8b1d2

O seu algoritmo receberá um array de inteiros, e deverá retornar uma arvore binária de busca.

```
type BinarySearchTree struct {
  value int
  left BinarySearchTree
  right BinarySearchTree
}
```

## Exemplo 01

Input: `K = [ 2, 3, 1, 4, 6, 7 ]`

Output:

```
{
  "value": 2,
  "left": {
    "value": 1,
    "left": null,
    "right": null
  },
  "right": {
    "value": 3,
    "left": null,
    "right": {
      "value": 4,
      "left": null,
      "right": {
        "value": 6,
        "left": null,
        "right": {
          "value": 7,
          "left": null,
          "right": null
        }
      }
    }
  }
}
```

## Desafio bônus 01:

Implemente um algoritmo de busca na árvore binária de busca (retorne true para existente e false para não existente).

## Exemplo 02

Input: `K = [ 2, 3, 1, 4, 6, 7 ]`

Output:

```
tree := FromArrayToBinarySearchTree(K)

SearchBinarySearchTree(tree, 1) // retorna true
SearchBinarySearchTree(tree, 9) // retorna false
```

## Desafio bônus 02:

Implemente uma forma de balancear a árvore para que ela não fique um lado muito maior que o outro.

## Exemplo 03

Input: `K = [ 2, 3, 1, 4, 6, 7 ]`

Output:

```
{
  "value": 4,
  "left": {
    "value": 2,
    "left": {
      "value": 1,
      "left": null,
      "right": null
    },
    "right": {
      "value": 3,
      "left": null,
      "right": null
    }
  },
  "right": {
    "value": 7,
    "left": {
      "value": 6,
      "left": null,
      "right": null
    },
    "right": null
  }
}
```
