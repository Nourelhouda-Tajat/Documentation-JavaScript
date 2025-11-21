## Sujet : Variables : var, let, const

### Sous sujet : Variable var 

### Définition :
var est utilisé pour déclarer une variable. C’est l'ancienne façon de déclarer des variables (avant ES6/2015). Elle se comporte différemment de let et const au niveau du hoisting et de la portée.

### Syntaxe :
```javascript
var nomDeVariable = valeur;
```

### Cas d'Utilisation :
Nécessaire uniquement pour maintenir un code hérité ou compatibilité avec de très anciens environnements JavaScript.

À éviter dans le code ; préférez let ou const pour plus de prévisibilité.

### Exemples :
```javascript
var destinationsData = [];
```


### Sous sujet : Variable let 

### Définition :
let permet de déclarer une variable à portée de bloc (block scope), introduite avec ES6 (2015). Contrairement à var, la variable n’est accessible que dans le bloc { ... } où elle a été déclarée.

### Syntaxe :
```javascript
let nomDeVariable = valeur;
```

### Cas d'Utilisation :
À utiliser lorsqu’on souhaite que la valeur de la variable change pendant l’exécution, dans une portée de bloc (par exemple : dans une boucle ou après une condition).

Privilégier let pour toutes les variables qui sont censées être modifiable par la suite.

### Exemples :
```javascript
let passengerCount = 1;
```

### Sous sujet : Variable const 

### Définition :
const permet de déclarer une constante à portée de bloc. Une fois initialisée, la variable ne peut plus être réaffectée ; sa valeur ne peut pas changer (pour les types primitifs). Pour les objets ou tableaux, on ne peut pas réassigner mais on peut modifier le contenu interne.

### Syntaxe :
```javascript
const nomDeConstante = valeur;
```

### Cas d'Utilisation :
À utiliser pour les valeurs qui ne doivent jamais être réaffectées, pour garantir la sécurité et la lisibilité du code.

Privilégier const par défaut, sauf si la variable doit être modifiée.

### Exemples :
```javascript
const loginInfo = localStorage.getItem('dataLogin');
```

## Sujet : Types de Données

### Sous sujet : Types Primitifs

### Définition :
Les types primitifs sont des valeurs uniques et simples sans propriétés ni méthodes. JavaScript définit les types primitifs : string, number, boolean, bigint, symbol, null, et undefined.

### Syntaxe :
```javascript
let nomDeVariable = valeur;
```

### Cas d'Utilisation :
String : Stocker des textes comme les noms, emails, destinations, descriptions.

Number : Stocker les prix, les durées, les quantités, les indices.

Boolean : Représenter des états vrais/faux (confirmation, disponibilité).

Null : Signifier l'absence intentionnelle d'une valeur.

Undefined : Variable déclarée mais non initialisée.

Bigint : Stocker des identifiants très grands (IDs de booking).

Symbol : Créer des identifiants uniques (rarement utilisé dans les apps classiques).

### Exemples :
```javascript
let passengerCount = 1;
let selectedDestination = null; 
const destinationPrice = 2500;
```


### Sous sujet : Types Référence

### Définition :
Les types référence sont des types complexes qui peuvent stocker plusieurs valeurs et différents types de données ensemble. JavaScript dispose d'un type référence principal : l'objet. Les tableaux, fonctions, dates, et autres structures sont tous des objets. Contrairement aux primitifs, les types référence stockent une adresse mémoire qui pointe vers la valeur réelle.

### Syntaxe :
```javascript
const objet = {
  nomAttribue1: valeur,
  nomAttribue1: valeur,
  nomAttribue1: valeur,
  nomAttribue1: valeur
};
```

### Cas d'Utilisation :
Objet : Stocker des données structurées avec propriétés dédiées.

Tableau : Stocker une liste de valeurs .

Fonction : Définer du code réutilisable pour des opérations complexes.

Date : Gérer les dates de départ et de retour.

### Exemples :
```javascript
let destinationsData = [
  {
    id: "mars-001",
    name: "Mars",
    price: 5000,
    accommodations: ["acc-001", "acc-002"]
  },
  {
    id: "moon-001",
    name: "Moon",
    price: 3000,
    accommodations: ["acc-003"]
  }
];
```

### Sous sujet : Vérifier les Types avec typeof 

### Définition :
L'opérateur typeof retourne une chaîne de caractères qui représente le type de données d'une variable, d'un objet, d'une fonction ou d'une expression. C'est l'outil principal pour vérifier les types en JavaScript à l'exécution.

### Syntaxe :
```javascript
typeof variable;
// ou
typeof (expression);
```

### Cas d'Utilisation :
Vérifier le type d'une variable avant de l'utiliser.

Valider les données reçues (des formulaires).

Implémenter une logique conditionnelle basée sur le type.

Déboguer et comprendre les types de données.

### Exemples :
```javascript
typeof "Mars"; // Retourne "string"
typeof isConfirmed; // Retourne "boolean"
console.log(typeof totalPrice); // "number"
```