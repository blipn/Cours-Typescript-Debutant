## **Pré-introduction à TypeScript : JavaScript & développement web**

### **📌 Objectif**

Situer TypeScript dans l'évolution du JavaScript et du développement web moderne.

### **Le JavaScript, d'où ça vient ?**

* Créé par Brendan Eich en 1995 chez Netscape  
* Langage **interprété**, **faiblement typé**, pour le **navigateur**  
* D'abord conçu pour des **scripts simples**, devenu langage complet avec le temps

#### 1995 — Création express

* **Brendan Eich** invente JavaScript en **10 jours** chez **Netscape**.  
* Nom initial : **Mocha**, puis **LiveScript**, enfin **JavaScript** (choix marketing pour surfer sur la popularité de Java).  
* Objectif : rendre **les pages web interactives** dans le navigateur Netscape Navigator.

#### 1996 — Microsoft entre en jeu

* Microsoft crée une version propriétaire : **JScript** pour Internet Explorer.  
* Début de la **guerre des navigateurs** et du cauchemar des compatibilités.

#### 1997 — Standardisation

* JavaScript devient un standard via **ECMAScript** (géré par ECMA International).  
* **ECMAScript 1** sort en 1997.  
* Depuis, **JS = langage implémentant ECMAScript**.

#### 2000–2009 — Stagnation et AJAX

* Peu d'évolutions majeures.  
* Arrivée d'**AJAX** (Asynchronous JavaScript and XML) en 2005 → pages dynamiques sans rechargement.  
* Développement de bibliothèques comme **jQuery** pour cacher les incompatibilités navigateurs.

#### 2009 — Node.js & JavaScript côté serveur

* **Ryan Dahl** lance **Node.js**, basé sur le moteur **V8** de Google Chrome (2008).  
  * V8 compile directement le code JavaScript en code machine natif avant de l’exécuter, au lieu d'utiliser des techniques plus traditionnelles telles que l’interprétation du bytecode ou la compilation du programme complet en code machine et l’exécution à partir d’un système de fichiers. Le code compilé est optimisé dynamiquement au moment de l'exécution.  
* JavaScript sort du navigateur → **utilisation backend, CLI, desktop, etc.**

#### 2015 — Renaissance avec ECMAScript 6 (ES6)

* ES6 (aussi appelé ES2015) introduit :  
  * `let`, `const`, `arrow functions`  
  * modules (`import`, `export`)  
  * classes, promises, `Map`, `Set`, etc.  
* Marque un **tournant majeur** → langage moderne, structuré.

#### Depuis 2016 — Évolutions annuelles

* Nouvelles versions **chaque année** : ES2016, ES2017, etc.  
* Introduction progressive de :  
  * `async/await`, `optional chaining`, `nullish coalescing`, etc.  
  * Classes privées, records & tuples (proposés), etc.

#### 2012–auj. — TypeScript et montée du typage

* Microsoft crée **TypeScript** pour sécuriser les projets JS.  
* Massivement adopté dans les frameworks modernes (Angular, NestJS, etc.)

#### Aujourd’hui

* JavaScript est **le langage le plus utilisé au monde** (source : Stack Overflow surveys).  
* Utilisé dans : **web, mobile (React Native), backend, IoT, desktop (Electron)**.  
* Le typage devient la norme avec TypeScript.  

### **Évolution du JavaScript moderne**

* **ES5 (2009)** : `Object.keys`, `strict mode`, base solide  
* **ES6 (2015)** : `let`, `const`, classes, modules, `arrow functions`, `Promise`  
* 15th Edition – **ECMAScript 2024**  
* Aujourd’hui : JS est partout (navigateur, backend via Node.js, mobile, desktop…)

### **Pourquoi JavaScript pose problème en projets complexes ?**

* Pas de typage strict → erreurs à l’exécution  
* Difficulté à maintenir des projets de grande taille  
* Mauvaise documentation des objets et fonctions via le code seul  
* Manque d’outils puissants d’autocomplétion / refactoring

### **TypeScript : réponse à ces limites**

* Créé par **Microsoft en 2012**  
* Superset de JavaScript  
  ✅ **Tout JavaScript valide est *syntaxiquement* valide en TypeScript**,  
  ⚠️ **Mais selon la configuration (`tsconfig.json`), certains comportements seront refusés à la compilation.**  
  Cela ne remet pas en cause le fait que TypeScript est bien un superset de JavaScript, mais cela souligne qu’il est **plus strict par défaut** pour garantir la qualité du code.  
* Apporte :  
  * ✅ **Typage statique**  
  * ✅ **Meilleure lisibilité du code**  
  * ✅ **Support puissant par les IDE (VS Code)**  
  * ✅ **Détection des erreurs à la compilation**

### **Où est utilisé TypeScript aujourd’hui ?**

* Presque tous les gros projets JS (Angular, NestJS, VSCode, Deno…)  
* Utilisé autant côté **frontend** (React, Angular…) que **backend** (Node.js, NestJS…)  
* Standard dans l’industrie (favorisé dans les équipes tech sérieuses)

### **Objectif du cours**

* Apprendre à utiliser **le typage comme outil de conception**  
* Savoir créer un **projet réel** (ex: API backend typée)  
* Être capable de **lire et écrire** du code TS moderne dans un contexte pro

## **Introduction à TypeScript**

### **📌 Objectif**

Comprendre ce qu'est TypeScript, ses avantages concrets, et comment il s'intègre dans l'écosystème JavaScript.

### **TypeScript, c'est quoi ?**

* Un **sur-ensemble de JavaScript** : tout code JS valide est du TS  
* Introduit un **typage statique** facultatif : on peut ajouter des types partout (ou nulle part)  
* Se **transpile en JavaScript** (via `tsc`) pour être exécuté dans un navigateur ou Node.js

### **Pourquoi utiliser TypeScript ?**

* ✅ **Erreurs captées avant l'exécution** (compilation)  
* ✅ **Aide à l'auto-complétion** dans les IDE  
* ✅ **Documentation implicite** grâce aux types  
* ✅ **Lisibilité accrue** pour les équipes et projets à long terme  
* ✅ **Refactoring plus sûr et plus rapide**

### **Ce que TypeScript n'est pas**

* ❌ Ce n'est pas un langage à part : il ne remplace pas JavaScript  
* ❌ Ce n'est pas un compilateur vers du binaire : il **génère du JS**  
* ❌ Il n'améliore pas les performances à l'exécution : il aide au **développement**, pas à l'exécution

### **Fonctionnement global de TypeScript**

* ✅ Tu écris du `.ts` (avec typage)  
* ✅ Le compilateur `tsc` génère du `.js` utilisable directement  
* ✅ Tu peux aussi exécuter via `ts-node` pour du dev rapide

### **Un premier exemple simple**

```js
function greeter(person: string) {  
 return `Hello ${person}`  
}  
console.log(greeter("world"))
```

### **Ce que vous allez apprendre ensuite**

* Comment configurer un projet TypeScript  
* Les types de base (string, number, boolean, etc.)  
* Les fonctions typées, interfaces, classes, modules  
* Comment construire un vrai projet typé (API, ou autre)

## **Mise en place de l'environnement TypeScript**

### **📌 Objectif**

Créer un environnement de développement TypeScript fonctionnel et minimal pour bien démarrer les exercices et projets.

### **Installer Node.js et npm**

Choix 1 :

* Aller sur : [https://nodejs.org](https://nodejs.org/)  
* Installer la version LTS (recommandée pour la stabilité)

Choix 2 : (**Recommandé**)

(windows)  
[https://github.com/coreybutler/nvm-windows/releases](https://github.com/coreybutler/nvm-windows/releases)  [nvm-setup.exe](https://github.com/coreybutler/nvm-windows/releases/download/1.2.2/nvm-setup.exe)

(linux + bashrc)
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash  
source ~/.bashrc # refresh le terminal
```

Installation et sélection d’une version de node
```
nvm install --lts  
nvm use 22.16.0
```

Vérifier l'installation  
```
node -v  
npm -v
```

En cas d’erreur (UnauthorizedAccess) sous windows  
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser

* Toujours prêter attention aux retours console 

### **Installer TypeScript globalement (CLI)**
```
npm install -g typescript
```
Vérifier l'installation  
```
tsc -v
```

### **Initialiser un projet TypeScript**
```
mkdir mon-projet-ts  
cd mon-projet-ts  
npm init -y
```

### **Créer et configurer `tsconfig.json`**

Initialiser TypeScript sur le repo  
```
tsc –init
```
* Options essentielles dans **tsconfig.json** :  
  * `target`: version JS à produire (ex: `ES2020`)  
  * `module`: système de module (ex: `commonjs` pour Node)  
  * `strict`: active les vérifications strictes (conseillé)  
  * `outDir`: répertoire de sortie JS (ex: `dist/`)  
  * `rootDir`: répertoire source (ex: `src/`)

### **Compiler et exécuter un fichier TS**
```
tsc  # compile vers /dist si configuré  
node dist/index.js
```
Ou en développement rapide avec `ts-node` :
```
npm install --save-dev ts-node  
npx ts-node src/index.ts
```
### **Editeur recommandé : VS Code**

* Autocomplétion et intégration TypeScript native  
* Formatage, erreurs, et navigation rapide  
* Extensions utiles : ESLint, Prettier, Path Intellisense

## **Types de base et syntaxe**

### **📌 Objectif**

Apprendre à utiliser les types fondamentaux de TypeScript pour définir des variables, fonctions et structures de données.

### **Types primitifs**

```js
let age: number = 25;  
let name: string = "Alice";  
let isActif: boolean = true;  
let nothing: null = null;  
let unknown: undefined = undefined;
```

### **Tableaux et tuples**

```js
let numbers: number[] = [1, 2, 3];  
let names: Array<string> = ["Alice", "Bob"];

let person: [string, number] = ["Alice", 25] // Tuple
```

### **Enumérations**

```js
enum Status {  
  ON,  
  OFF,  
  PAUSED,  
}

let status: Status = Status.ON
```

Alternative couramment utilisée

```js
type Status = 'on' | 'off' | 'paused'  
let status: Status = 'on'
```

Alternative idéale

```js
const Status = { // Définition JS  
  ON: 'on',  
  OFF: 'off',  
  PAUSED: 'paused',  
} as const; // On force la constante de la valeur  
type Status = typeof Status[keyof typeof Status]; // Création du type Status

// Utilisation du Type et de l'objet Status  
let status: Status = Status.PAUSED  
Object.entries(Status).forEach(([key, value]) => {  
  console.log(`${key} → ${value}`);  
});
```

### **Alias de types et interfaces**

```js
type Id = number;  
interface User {  
  id: Id;  
  name: string;  
  active: boolean;  
}
```

### **Types unions et intersections**

```js
// Union : une chose ou une autre  
let id: number | string = 42;  
id = "abc";

// Intersection : combine les types  
interface A {  
  a: string;  
}  
interface B {  
  b: number;  
}  
let obj: A & B = { a: "test", b: 123 };
```

### **Typage implicite et explicite**

```js
let a = 5;        // Type inféré : number  
let b: string;    // Type explicite  
b = "ok";
```

### **Astuces et erreurs courantes**

* Ne pas confondre `null` et `undefined`  
* Bien typer les tableaux  
* Penser à utiliser des `type` ou `interface` pour les objets complexes  
* Laisser l'inférence faire le travail quand c'est évident

### **Exercice simple proposé**

Créer une interface `Product` avec   
`id`, `name`, `price`, `available`,   
et un tableau de `Product[]` avec 2 produits typés.

## **Fonctions et portée**

### **📌 Objectif**

Comprendre comment typer correctement des fonctions en TypeScript, utiliser les paramètres optionnels ou par défaut, et maîtriser la portée des variables.

### **Signatures de fonction**

```js
function addition(a: number, b: number): number {  
  return a + b;  
}  
// Type des paramètres et du retour obligatoires
```

### **Paramètres optionnels et valeurs par défaut**

```js
function sayHello(name?: string): string {  
  return "Hello " + (name ?? "unknown");  
}  
// name est facultatif

function mult(a: number, b: number = 2): number {  
  return a * b;  
}  
// b est facultatif
```

### **Fonctions fléchées (arrow functions)**

```js
const double = (x: number): number => x * 2;
```

Syntaxe concise, lie le `this` lexicalement

### **Typage d'une fonction stockée dans une variable**

```js
const operation: (x: number, y: number) => number = (x, y) => x + y;
```

### **Typage d'une fonction asynchrone**

```js
const operation: (x: Promise<number>, y: number) => Promise<number> =   
async (x, y) => { return await x + y};
```

### **Inférence de type**

```js
function square(x: number) {  
  return x * x; // Type du retour inféré automatiquement : number  
}
```

TypeScript infère souvent correctement le type de retour

### **La portée des variables**

* `let` et `const` ont une **portée de bloc** (comme en C, Java...)  
* `var` a une portée fonctionnelle (ancien JS, à éviter)

```js
function example() {  
  if (true) {  
    let x = 10;  
    const y = 20;  
  }  
  // console.log(x); // Erreur : x est hors de portée ici  
}
```

### **Astuces & erreurs courantes**

* Toujours typer le retour de fonction si l'inférence est ambiguë  
* Ne jamais utiliser `any` par défaut  
* Préférer `const` pour la définition d’une variable

### **Exercice simple proposé**

Créer une fonction `displayProduct(p: Product)` qui retourne une chaîne avec le nom et le prix d'un produit (type `Product` vu précédemment).

## **Classes et programmation orientée objet (POO)**

### **📌 Objectif**

Comprendre la définition et l'utilisation des classes, modificateurs d'accès, héritage, et interfaces avec TypeScript.

### **Définir une classe simple**

```js
class Animal {  
  name: string;

  constructor(name: string) {  
    this.name = name;  
  }

  makeNoise(): void {  
    console.log(`${this.name} fais du bruit`);  
  }  
}

const a = new Animal("Chien");  
a.makeNoise();
```

### **Modificateurs d'accès**

```js
class Person {  
  public name: string;  
  private age: number;  
  protected email: string;

  constructor(name: string, age: number, email: string) {  
    this.name = name;  
    this.age = age;  
    this.email = email;  
  }  
}
```
* `public` : accessible partout **(valeur par défaut)**  
* `private` : accessible uniquement dans la classe  
* `protected` : accessible dans la classe et ses enfants

### **Propriétés readonly**

```js
class Livre {  
  readonly isbn: string;  
  constructor(isbn: string) {  
    this.isbn = isbn;  
  }  
}
```
Impossible de modifier `isbn` après initialisation

### **Héritage et surcharge**

```js
// On réutilise la class Animal  
class Dog extends Animal {  
  makeNoise(): void {  
    console.log(this.name + " : Wouf");  
  }  
}

const d = new Dog("Chien");  
d.makeNoise() // log "Chien : Wouf"
```

### **Interfaces comme contrat de classe**

```js
interface Vehicle {  
  brand: string;  
  start(): void;  
}

class Car implements Vehicle {  
  brand: string;  
  constructor(brand: string) {  
    this.brand = brand;  
  }  
  start(): void {  
    console.log("La voiture démarre");  
  }  
}

const myCar = new Car('Audi')  
myCar.start()
```

### **Astuces et erreurs courantes**

* Ne pas abuser de l'héritage : utiliser la composition quand c'est possible  
* Toujours initialiser les propriétés dans le constructeur  
* `implements` ≠ `extends`  
  **⚠️ Obligation d’implémenter toutes les propriétés et méthodes de l’interface**  
  **✅ Aucune obligation lors de l’extends**

### **Exercice proposé**

Créer une classe `Product` avec `id`, `name`, `price` et une méthode `display()`. Puis créer une sous-classe `OnSaleProduct` avec un prix réduit.

## **Modules et organisation du code**

### **📌 Objectif**

Apprendre à structurer un projet TypeScript avec des modules clairs et réutilisables.

### **Import et export**

```js
// math.ts
export function add(a: number, b: number): number {  
  return a + b;  
}

export function mult(a: number, b: number): number {  
  return a * b;  
}
```


```js
// main.ts
import { add } from "./math";  
console.log(add(2, 3));
```

* `export` rend disponible une fonction/classe/type à l’extérieur  
* `import` permet de l'utiliser dans un autre fichier

Alternative d’export

```js
function add(a: number, b: number): number {  
  return a + b;  
}

function mult(a: number, b: number): number {  
  return a * b;  
}

export { add, mult }
```

### **Types d'export**

* **Nomé** : `export function f()` → `import { f } from "..."`  
* **Par défaut** : `export default f` → `import f from "..."`

Privilégier les exports nommés pour la lisibilité et l'autocomplétion

### **Gestion des dépendances avec npm**

```
lodash est une librairie qui fournit certaines fonctions utilitaires  
npm install lodash  
npm install --save-dev @types/lodash
```

`--save-dev` pour les types ou outils de développement

### **Bonnes pratiques d'organisation**

* Garder un fichier = un rôle (principe de responsabilité unique)  
* Nommer clairement les fichiers selon leur contenu  
* Utiliser des dossiers pour regrouper les concepts  
* Ne jamais tout mettre dans `index.ts`

### **Exercice proposé**

Créer un dossier `models/` contenant une interface `Product`. Dans `services/`, créer une fonction `computePriceWithTaxes(product: Product): number`.

## **Outils et bonnes pratiques**

### **📌 Objectif**

Améliorer la qualité, la lisibilité et la maintenabilité du code TypeScript avec des outils modernes et des pratiques efficaces.

### **Linter avec ESLint**

```
npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin  
npx eslint --init
```

* Utiliser le parseur `@typescript-eslint/parser`  
* Ajouter le plugin `@typescript-eslint`  
* Exemple de règles utiles :

```json
{  
  "extends": ["eslint:recommended", "plugin:@typescript-eslint/recommended"]  
}
```

### **Formatter avec Prettier**

```
npm install --save-dev prettier
```

Créer un fichier `.prettierrc` avec des règles simples :

```json
{  
  "semi": true,  
  "singleQuote": true,  
  "tabWidth": 2  
}
```

Peut s’intégrer à ESLint ou s’utiliser seul

### **Compilation/transpilation**

* `tsc` (natif, simple)  
* `ts-node` (dev rapide)  
* Autres options pour projets complexes : Webpack, Vite, esbuild...

### **Tests unitaires avec Jest**

```
npm install --save-dev jest ts-jest @types/jest  
npx ts-jest config:init
```

Ecrire un test simple :
```js
// addition.test.ts  
import { addition } from './addition';

test('addition de 2 + 3', () => {  
  expect(addition(2, 3)).toBe(5);  
});
```

### **Bonnes pratiques de code**

✅ Préférer `const` à `let` (immutabilité)  
✅ Eviter `any`, utiliser `unknown` ou des types précis  
✅ Utiliser des noms explicites (fonctions, variables, fichiers)  
✅ Factoriser les types répétés (avec `type` ou `interface`)  
✅ Commenter le "pourquoi", pas le "quoi"

### **Exercice proposé**

Configurer ESLint + Prettier sur le projet TypeScript, avec une règle personnalisée (ex : forcer le point-virgule). Ajouter une série de tests au précédent exercice.

## **Utiliser TypeScript avec des bibliothèques existantes**

### **📌 Objectif**

Comprendre comment utiliser des bibliothèques JavaScript tierces en TypeScript en profitant du typage.

### **Le problème**

* Beaucoup de bibliothèques JS ne sont pas écrites en TypeScript  
* TypeScript ne peut pas automatiquement connaître les types → besoin de **fichiers de définition**

### **Les types « DefinitelyTyped » (`@types/...`)**

```
npm install lodash  
npm install --save-dev @types/lodash
```

* Les types sont séparés pour les bibliothèques JS classiques  
* On les installe comme des dépendances de développement

### **Typage automatique pour les bibliothèques écrites en TS**

* Si une lib est écrite en TS (ex: Axios, React), pas besoin d’installer `@types/...`

### **Créer ses propres définitions simples**

Typage d’une lib JS non typée

```js
// types.d.ts  
declare module "ma-lib-js" {  
  export function magie(x: number): string;  
}
```

* Pour les cas rares où aucune définition n’existe  
* À inclure via `tsconfig.json` ou directement dans `src/`  
* Permet à TypeScript de ne pas lever d’erreur quand tu utilises "ma-lib-js"  
* Active l’autocomplétion et le typage dans ton IDE

### **Partager des types globalement**

```js
// types.d.ts  
interface Product {  
  id: number;  
  name: string;  
  price: number;  
}
```

* Tu peux utiliser `Produit` dans n’importe quel fichier `.ts` du projet sans import.  
* ⚠️ Mais attention : c’est **global**, donc **à éviter** dans les gros projets.  
* Mieux vaut utiliser `export interface` dans un fichier de type `models/produit.ts`

### **Exemple d'utilisation typée**

```js
import _ from 'lodash';

type Product = { id: number; name: string; price: number };

const products: Product[] = [  
  { id: 1, name: 'Pen', price: 1.2 },  
  { id: 2, name: 'Notebook', price: 2.5 },  
  { id: 3, name: 'Pen', price: 1.1 },  
];

// Group products by name  
const grouped = _.groupBy(products, (p) => p.name);

// Example: get all pens  
const pens = grouped['Pen'] ?? [];

pens.forEach((p) => {  
  console.log(`${p.name} - €${p.price}`);  
});
```

### **Erreurs classiques**

* Oublier `@types/...` pour une lib JS → erreurs de compilation  
* Installer des `@types/...` inutiles pour une lib déjà typée

### **Exercice proposé**

Installer la bibliothèque `date-fns`, ajouter ses types, puis créer une fonction typée `formatDate(date: Date): string` qui renvoie la date au format "dd/MM/yyyy".

## **Projet pratique**

### **📌 Objectif**

Mettre en application les compétences acquises en TypeScript dans un petit projet concret.

### **Sujet possible : Gestion de produits / articles**

Créer une mini API ou structure d'application permettant de gérer une liste de produits avec nom, prix, disponibilité, etc.

### **Objectifs du projet**

* Définir des **interfaces** et **types** clairs  
* Structurer le code en **modules** (fichiers / dossiers)  
* Manipuler les données avec des **fonctions typées**  
* Gérer les cas d'erreurs via les types ou des retours explicites

### **Fonctions demandées**

* `addProduct(p: Product): void`  
* `listProducts(): Product[]`  
* `findProduct(id: number): Product | undefined`  
* `computeTaxOnProduct(p: Product): number`

### **Extensions possibles (si temps disponible)**

* Créer une classe `OnSaleProduct` héritant de `Product`  
* Ajouter un module `utils/format.ts` pour formater les prix  
* Écrire quelques unitaires avec Jest

### **Variante avec une mini API (optionnelle)**

* Utiliser `express` + `ts-node` pour créer une API REST simple  
  * `GET /products`  
  * `POST /products`  
  * `GET /products/:id`

* Utiliser des types pour les requêtes et réponses

### **Critères de validation**

* Le code compile sans erreur  
* Les types sont précis, pas de `any`  
* Le projet est organisé, modulaire, lisible  
* Bonus : documentation dans un `README.md`

### **Livrable attendu**

Dossier compressé `.zip` contenant le projet complet ou lien GitHub

### **Rappel des compétences mobilisées**

* Typage statique, fonctions, classes, interfaces, modules, outils (linter, prettier, tests)

## **Ressources**

**TS Playground**   
[https://www.typescriptlang.org/play/](https://www.typescriptlang.org/play/)

**Documentation :**  
[https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html](https://www.typescriptlang.org/docs/handbook/typescript-from-scratch.html)  
[https://typestrong.org/ts-node/docs/](https://typestrong.org/ts-node/docs/)

**CheatSheets** :  
[https://www.typescriptlang.org/fr/cheatsheets/](https://www.typescriptlang.org/fr/cheatsheets/)  
[https://rmolinamir.github.io/typescript-cheatsheet/](https://rmolinamir.github.io/typescript-cheatsheet/)

**Aller plus loin :**  
[https://docs.nestjs.com/](https://docs.nestjs.com/)  
[https://react.dev/learn/typescript](https://react.dev/learn/typescript)  
[https://docs.deno.com/runtime/](https://docs.deno.com/runtime/)  
[https://nodejs.org/en/learn/typescript/run-natively](https://nodejs.org/en/learn/typescript/run-natively)  
