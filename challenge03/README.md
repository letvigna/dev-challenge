# Desafio 03 - SearchPokemon (23/05/2022):

O desafio dessa semana é temático de Pokemon:

Dada a estrutura de dados abaixo, onde temos o numero na pokedex, o nome, a as evoluções anterior, e posteriores.

```
type Pokemon {
  dex: number
  name: string
  prevEvo: number[]
  nextEvo: number[]
}
```

Escreva um algoritmo que receba como parâmetro dois tipos de pesquisas:

1. Tipo `exact`, onde você vai pesquisar pokemons que contenham o trecho da busca enviado (veja exemplo 01 onde foi pesquisado por “al”).

2. Tipo `evolution`, onde além de pesquisar o o trecho de busca(igual o tipo 1), você vai retorna também todas as possíveis evoluções, tanto pregressas quanto posteriores (veja exemplos 02 onde retornamos a linha evolutiva do Ralts).

Perceba, que se você pesquisar por um pokemon no fim da cadeia evolutiva, e ele tiver outras opções, você deve retornar todas as evoluções anteriores (veja exemplo 03). E a busca deve ser ordenada pelo numero na dex (veja exemplo 04).

## Dataset

```
const miniDex = []Pokemon {
  Pokemon {
    dex: 35,
    name: "Clefairy",
    prevEvo: [173],
    nextEvo: [36],
  },
  Pokemon {
    dex: 36,
    name: "Clefable",
    prevEvo: [35],
    nextEvo: [],
  },
  Pokemon {
    dex: 133,
    name: "Eevee",
    prevEvo: [],
    nextEvo: [134, 135, 136, 196, 197, 470, 471, 700],
  },
  Pokemon {
    dex: 134,
    name: "Vaporeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 135,
    name: "Jolteon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 136,
    name: "Flareon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 173,
    name: "Cleffa",
    prevEvo: [],
    nextEvo: [35],
  },
  Pokemon {
    dex: 183,
    name: "Marill",
    prevEvo: [298],
    nextEvo: [184],
  },
  Pokemon {
    dex: 184,
    name: "Azumarill",
    prevEvo: [183],
    nextEvo: [],
  },
  Pokemon {
    dex: 196,
    name: "Espeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 197,
    name: "Umbreon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 280,
    name: "Ralts",
    prevEvo: [],
    nextEvo: [281],
  },
  Pokemon {
    dex: 281,
    name: "Kirlia",
    prevEvo: [280],
    nextEvo: [282, 475],
  },
  Pokemon {
    dex: 282,
    name: "Gardevoir",
    prevEvo: [281],
    nextEvo: [],
  },
  Pokemon {
    dex: 298,
    name: "Azurill",
    prevEvo: [],
    nextEvo: [183],
  },
  Pokemon {
    dex: 470,
    name: "Leafeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 471,
    name: "Glaceon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 475,
    name: "Gallade",
    prevEvo: [281],
    nextEvo: [],
  },
  Pokemon {
    dex: 700,
    name: "Sylveon",
    prevEvo: [133],
    nextEvo: [],
  },
}
```

## Exemplo 01

Input: `SearchPokemon("exact", miniDex, "al")`

Output:

```
[
  Pokemon {
    dex: 280,
    name: "Ralts",
    prevEvo: [],
    nextEvo: [281],
  },
  Pokemon {
    dex: 475,
    name: "Gallade",
    prevEvo: [281],
    nextEvo: [],
  },
]
```

## Exemplo 02

Input: `SearchPokemon("evolution", miniDex, "al")`

Output:

```
[
  Pokemon {
    dex: 280,
    name: "Ralts",
    prevEvo: [],
    nextEvo: [281],
  },
  Pokemon {
    dex: 281,
    name: "Kirlia",
    prevEvo: [280],
    nextEvo: [282, 475],
  },
  Pokemon {
    dex: 282,
    name: "Gardevoir",
    prevEvo: [281],
    nextEvo: [],
  },
  Pokemon {
    dex: 475,
    name: "Gallade",
    prevEvo: [281],
    nextEvo: [],
  },
]
```

## Exemplo 03

Input: `SearchPokemon("evolution", miniDex, "sylveon")`

Output:

```
[
  Pokemon {
    dex: 133,
    name: "Eevee",
    prevEvo: [],
    nextEvo: [134, 135, 136],
  },
  Pokemon {
    dex: 134,
    name: "Vaporeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 135,
    name: "Jolteon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 136,
    name: "Flareon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 196,
    name: "Espeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 197,
    name: "Umbreon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 470,
    name: "Leafeon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 471,
    name: "Glaceon",
    prevEvo: [133],
    nextEvo: [],
  },
  Pokemon {
    dex: 700,
    name: "Sylveon",
    prevEvo: [133],
    nextEvo: [],
  },
]
```

## Exemplo 04

Input: `SearchPokemon("evolution", miniDex, "cleffa")`

Output:

```
[
  Pokemon {
    dex: 35,
    name: "Clefairy",
    prevEvo: [173],
    nextEvo: [36],
  },
  Pokemon {
    dex: 36,
    name: "Clefable",
    prevEvo: [35],
    nextEvo: [],
  },
  Pokemon {
    dex: 173,
    name: "Cleffa",
    prevEvo: [],
    nextEvo: [35],
  },
]
```

## Bonus round:

Permita que seu algoritmo além de receber o nome, também receba o dex number.
