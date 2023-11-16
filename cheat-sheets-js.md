# Cheat sheets js

## Fondamentaux 
  
### Conversions  
  
Conversion en String :  
```js
let Variable = 0;
let VariableString = Variable.toString();
// ou
let VariableString = String(Variable);
```

Conversion en Number :  
```js
let Variable = "String";
let VariableNumber = +Variable
// ou
let VariableString = Number(Variable);
```  
  
Conversion en Boolean :  
```js
let Variable = "0";
let TrueOrFalse = Boolean(Variable);
// ou
let TrueOrFalse = !!Variable;
```  

### Opérateur Mathématiques  
  
Addition `+`  
Soustraction `-`  
Multiplication `*`  
Division `/`  
Reste `%`  
Exponentiation `**`  

### Concaténation  
  
```js
let conca = "my" + "string"
return conca; // conca return "mystring"
```  
  
### Incrémentation  
  
```js
let counter = 2;
counter++;        // fonctionne de la même manière que counter = counter + 1, mais c'est plus court
alert( counter ); // 3
```  
  
```js
let counter = 2;
counter--;        // fonctionne de la même manière que counter = counter - 1, mais c'est plus court
alert( counter ); // 1
```  
  
```js
let counter = 1;
let a = ++counter; // a = counter + 1

alert(a); // 2
```  
  
```js
let counter = 1;
let a = counter++; // a = counter puis counter = counter + 1

alert(a); // 1
```  

### Comparaisons  
  
Plus grand ou plus petit : `a > b`,`a < b`  
Plus grand ou égale, plus petit ou égale : `a >= b`,`a <= b`  
Egalité : `a == b`  
Pas égal : `a != b`  
  
### Condition : if, ?, switch
  
Version "if"   
```js
if (years == 2023) {
    return true
} else {
    return false
}
```  
  
Version ternaire "?"  
```js
let result = years == 2023 ? return true : return false;
```  
  
Version Switch  
  
```js
Switch (years){
    case 2023 :
        return "On est en 2023";
        break;
    case 2024 :
        return "On est en 2024";
        break;
    default :
        return "Valeur si aucune correspondance"
        break;
}
```  
  
### Opérateurs logique
  
Or, ||  
```js
alert( true  || true  ); // true
alert( false || true  ); // true
alert( true  || false ); // true
alert( false || false ); // false
```  
Il cherche la vérité.  
  
And, &&  
```js
alert( true  && true  ); // true
alert( false && true  ); // false
alert( true  && false ); // false
alert( false && false ); // false
```  
Il cherche l'erreur.  
  
Not, !  
```js
alert( !true ); // false
alert( !0 ); // true
```  
  
### Boucle
  
```js
let i = 0;
while (i < 3) { // affiche 0, puis 1, puis 2
  alert( i );
  i++;
}
```  
  
```js
let i = 0;
do {
  alert( i );
  i++;
} while (i < 3);
```  
  
```js
for (let i = 0; i < 3; i++) { // affiche 0, puis 1, puis 2
  alert(i);
}
```  
  
On peut briser une boucle avec `break;`  
  
## Fonction  
  
Fonction déclaration  
```js
function sum(a, b) {
  return a + b;
}
```  
  
Fontion expression
```js
let sum = function(a, b) {
  return a + b;
};
```  
  
Fonction fléchées  
```js
let sum = (a, b) => a + b;
```  
  
## Tableau  
  
### déclarer un tableau  
  
```js
let arr = [];
```  
  
```js
let fruits = ["Apple", "Orange", "Plum"];

alert( fruits[0] ); // Apple
alert( fruits[1] ); // Orange
alert( fruits[2] ); // Plum
```  
  
### Supprimé un élément du tableau  
  
```js
arr.splice(start[, deleteCount, elem1, ..., elemN])
```  
  
exemple :  
```js
let arr = ["I", "study", "JavaScript"];

arr.splice(1, 1); // À partir de l'index 1 supprime 1 élément

alert( arr ); // ["I", "JavaScript"]
```  

### Ajouter un élément dans un tableau  
  
```js
let arr = ["I", "study", "JavaScript"];

// de l'index 2
// supprime 0
// et ajoute "complex" et "language"
arr.splice(2, 0, "complex", "language");

alert( arr ); // "I", "study", "complex", "language", "JavaScript"
```  
  
### Cloner un tableau  
  
```js
arr.slice([start], [end])
```  
  
### .map appliqué une fonction à toute les index d'un tableau  
  
```js
const numbers = [1, 2, 3, 4, 5];
const squaredNumbers = numbers.map(num => num ** 2);

// squaredNumbers sera [1, 4, 9, 16, 25]
```  
  
### trié un tableau  
  
```js
function compareNumeric(a, b) {
  if (a > b) return 1;
  if (a == b) return 0;
  if (a < b) return -1;
}

let arr = [ 1, 2, 15 ];

arr.sort(compareNumeric);

alert(arr);  // 1, 2, 15
```  
  
### inverser  
  
```js
let arr = [1, 2, 3, 4, 5];
arr.reverse();

alert( arr ); // 5,4,3,2,1
```  
  
### Diviser
  
Divise et un créer un nouveau tableau
```js
let str = "test";

alert( str.split('') ); // t,e,s,t
```  
  
### rassemble  
  
Forme un String à base d'un tableau
```js
let arr = ['Bilbo', 'Gandalf', 'Nazgul'];

let str = arr.join(';'); // joint les éléments du tableau en une string en utilisant le caractère ";"

alert( str ); // Bilbo;Gandalf;Nazgul
```  
  
### Cumule   
  
```js
let arr = [1, 2, 3, 4, 5];


let result = arr.reduce((sum, current) => sum + current, 0;

alert( result ); // 15
```  

```js
const grades = [90, 85, 75, 92, 88];

const average = grades.reduce((sum, grade) => sum + grade, 0) / grades.length;
//                                                         ^
//                                       Initial value of the accumulator

// La valeur initiale de `sum` est 0.

// Première itération : sum = 0 + 90 = 90
// Deuxième itération : sum = 90 + 85 = 175
// Troisième itération : sum = 175 + 75 = 250
// Quatrième itération : sum = 250 + 92 = 342
// Cinquième itération : sum = 342 + 88 = 430

// À la fin, la valeur de `sum` est 430.
```  

