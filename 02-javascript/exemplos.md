## Funções
> São muito utilizadas no dia dia, vamos dar alguns exemplos de declarações de funções.

```javascript
console.log('oii'); // oii
```

> Exemplos: ES5
```javascript
var x = function(x, y) {
     return x * y;
}
```

```javascript
function x(a, b) {
    return a * b;
}
```
> Exemplo: ES6 | Arrow Functions
```javascript
const x = (x, y) => x * y;
```

```javascript
function myFunction(x, y = 10) {
    // y é por default
    return x + y;
}
myFunction(5); // 15
```

## String
```javascript

const hello = "hello, world";

hello.replace("hello", "goodbye"); // goodbye, world

"hello".toUpperCase(); // HELLO

```

## Objetos

> Exemplo: Aqui podemos criar objetos (entidades)
```javascript
const pessoa = {
  nome: 'Jorge',
  idade: 28,
  cargo: 'Desenvolvedor'
};
console.log(pessoa.nome); // Jorge
```

## Comparação

> Exemplo: Aqui comparamos se a idade é menor que 18
```javascript
const age = 18;
if (age < 18) {
    return "Jovem";
} else {
    return "Adulto";
}
```

## Condição Ternária
> Exemplo: Fazemos o mesmo utilizando apenas uma linha
```javascript
const age = 18;
const pessoa = (age < 18) ? "Jovem": "Adulto";
```

## Rest Params
> Exemplo: Podemos passar vários argumentos
```javascript
function(a, b, ...args) {
  // .console.log(a) = ?
  // .console.log(b) = ?
  // .console.log(args) = [];
}
```

## Destruct
> Você pode quebrar um objeto, separando seus atributos.
```javascript
const pessoa = {
  nome: 'Jorge',
  idade: 28,
  cargo: 'Desenvolvedor'
};

const { nome, idade, cargo } = pessoa;
console.log(nome); // Jorge
console.log(idade); // 28
console.log(cargo); // Desenvolvedor


const { nome, ...rest } = pessoa;
console.log(nome); // Jorge
console.log(rest.idade); // 28
console.log(rest.cargo); // Desenvolvedor
---

const numeros = [1,2,3];
const [a, b, c] = numeros;
console.log(a, b, c) // 1, 2, 3


const numeros = [1,2,3];
const [a, ...rest] = numeros;
console.log(a, b, c) // a, [2,3]

```
## CallBack
```javascript
(() => {
    console.log('exemplo de callback');

    getLista(5, (err, result) => {
        if (err) {
            console.error(err);
            return;
        }

        console.log(result);
    })

})();

function getLista(qtd, callback) {
    const lista = [];

    for (let i = 0; i < qtd; i++) {
        lista.push(i);
    }

    if (lista.length > 5) {
        return callback(new Error('limite excedido de lista'), null);
    }

    return callback(null, lista);
}
```

## Promise
```javascript
(() => {
    console.log('exemplo de promise');

    getLista(5)
        .then((result) => {
            return console.log(result);
        })
        .catch((err) => {
            return console.error(err);
        })

})();

function getLista(qtd) {
    return new Promise((resolve, reject) => {
        const lista = [];

        for (let i = 0; i < qtd; i++) {
            lista.push(i);
        }

        if (lista.length > 5) {
            return reject(new Error('limite excedido de lista'));
        }

        return resolve(lista);
    })
}
```

## Async
```javascript
(async () => {
    console.log('exemplo de async await');

    let promises = [];

    promises.push(getLista(2));
    promises.push(getLista(5));

    const all = await Promise.all(promises);

    try {
        const result = await getLista(5);
        console.log(result);
    } catch (error) {
        console.error(error);
    }
})();

async function getLista(qtd) {
    const lista = [];

    for (let i = 0; i < qtd; i++) {
        lista.push(i);
    }

    if (lista.length > 5) {
        throw new Error('limite excedido de lista');
    }

    return lista;
}
```

// Para conseguir executar deixe descomentado somente 1 bloco por vez.
// FUNÇAO SIMPLES
// =====================================================================

// function soma(x, y) {
//   return x + y;
// }

// console.log('sem default =', soma(1,2));
// console.log('com default =',soma(1));
// console.log('com default =',soma(1, 'jorge'));
// console.log('com default =', soma(1, '1'));
// console.log('com default =', soma('1', 1));

// FUNÇÃO COM ARROW FUNCTION
// =====================================================================

// const x = (a, b) => { return a + b };
// console.log(x(1, 2));

// DESTRUCT DE ARRAY
// =====================================================================
// const values = [1, 2, 3, 4, 5];

// const [a, b, , c] = values

// CALLBACK SINCRONO (PARADIGMA FUNCIONAL)
// ===================================================================

// const t = (x, fun) => {
//   console.log(x);
//   fun(5, 5);
// }
// const soma = (h, t) => { console.log(h + t) }
// console.log(t('batata', soma));

// MANIPULAÇÃO DE ARRAY
// ================================================================
// const values = [1, 2, 3, 4, 5];
// const [a, b, ...rest] = values
// const lista = [];
// lista.push(a);
// lista.push(b);
// lista.push(...rest);
// console.log(lista);

// const filtrada = lista.filter((item) => item > 3);
// const mapa = lista.map((item, index) => {
//   return {
//     value: item,
//     index
//   }
// });
// console.log(mapa);

// MANIPULAÇÃO DE STRING
// ================================================================
// const batata = 'Batata';
// console.log(batata.toUpperCase());
// console.log(batata.toLowerCase());
// console.log(batata.replace(/t/g, 'r'));
// console.log(batata.indexOf('t'));

// MANIPULAÇÃO DE OBJETO
// =================================================================
// const Pessoa = {
//   nome: 'Jorge',
//   sobrenome: 'souza',
//   rg: 11111111
// }
// console.log(Pessoa);
// Pessoa.rg = 444444;
// console.log(Pessoa);

// CALLBACK
// ===============================================================
// (() => {
//   console.log('exemplo de callback');

//   getLista(5, (err, result) => {
//     if (err) {
//       console.error(err);
//       return;
//     }
//     getLista(5, (errB, resultB) => {
//       if (errB) {
//         console.error(errB);
//         return;
//       }
//       getLista(5, (errC, resultC) => {
//         if (errC) {
//           console.error(errC);
//           return;
//         }

//         console.log(resultC, resultB, result);
//       })

//       // console.log(resultB);
//     })
//     // console.log(result);
//   })

// })();

// function getLista(qtd, callback) {
//   const lista = [];

//   for (let i = 0; i < qtd; i++) {
//     lista.push(i);
//   }

//   if (lista.length > 5) {
//     return callback(new Error('limite excedido de lista'), null);
//   }

//   return callback(null, lista);
// }

// PROMISE
// ===================================================================
// (() => {
//   console.log('exemplo de promise');

//   getLista(5)
//     .then((result) => {
//       return getLista(5);
//     })
//     .then((result) => {
//       return console.log(result);
//     })
//     .catch((err) => {
//       return console.error(err);
//     })

// })();

// function getLista(qtd) {
//   return new Promise((resolve, reject) => {
//     const lista = [];

//     for (let i = 0; i < qtd; i++) {
//       lista.push(i);
//     }

//     if (lista.length > 5) {
//       return reject(new Error('limite excedido de lista'));
//     }

//     return resolve(lista);
//   })
// }

// ASYNC/AWAIT
// ====================================================================
// (async () => {
//   console.log('exemplo de async await');

//   let promises = [];

//   promises.push(getLista(2));
//   promises.push(getLista(5));

//   const all = await Promise.all(promises);

//   try {
//     const result = await all;
//     console.log(result);
//   } catch (error) {
//     console.error(error);
//   }
// })();

// async function getLista(qtd) {
//   const lista = [];

//   for (let i = 0; i < qtd; i++) {
//     lista.push(i);
//   }

//   if (lista.length > 5) {
//     throw new Error('limite excedido de lista');
//   }

//   return lista;
// }
// ====================================================================