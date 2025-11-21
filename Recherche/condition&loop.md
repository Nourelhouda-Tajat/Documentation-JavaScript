## Sujet : Instructions Conditionnelles

### Sous sujet : if/else et else if 

### Définition :
L'instruction if/else exécute un bloc de code si une condition est vraie. L'instruction else if permet de tester plusieurs conditions successivement, tandis que else capture les cas qui ne correspondent à aucune condition précédente

### Syntaxe :
```javascript
if (condition1) {
  // bloc exécuté si condition1 est TRUE
} else if (condition2) {
  // bloc exécuté si condition1 est FALSE et condition2 est TRUE
} else if (condition3) {
  // bloc exécuté si condition1 et condition2 sont FALSE et condition3 est TRUE
} else {
  // bloc exécuté si toutes les conditions précédentes sont FALSE
}
```

### Cas d'Utilisation :
Valider les données saisies dans un formulaire.

Vérifier les conditions avant d'exécuter une action.

### Exemples :
```javascript
// === VALIDATION D'EMAIL EN if/else ===
function validateEmail(email) {
  if (email && !regexEmail.test(email)) {
    showError(emailInput, "Invalid email format");
    return false;
  } else if (!email) {
    showError(emailInput, "Email is required");
    return false;
  } else {
    hideError(emailInput);
    return true;
  }
}

validateEmail("user@example.com");
```


### Sous sujet : switch

### Définition :
L'instruction switch exécute différents blocs de code selon différentes conditions. Elle compare une expression avec plusieurs valeurs (case) et exécute le code du cas correspondant. L'instruction switch est souvent plus lisible qu'une longue chaîne de if/else if.

### Syntaxe :
```javascript
switch (expression) {
  case valeur1:
    // Code exécuté si expression === valeur1
    break; // Important : stoppe l'exécution
  case valeur2:
    // Code exécuté si expression === valeur2
    break;
  case valeur3:
  case valeur4:
    // Code exécuté si expression === valeur3 OU valeur4
    break;
  default:
    // Code exécuté si aucun case ne correspond
}
```

### Cas d'Utilisation :
Traiter plusieurs cas discrets.

Remplacer une longue chaîne de if/else if pour plus de lisibilité.​

Sélectionner un chemin en fonction d'une valeur spécifique.

Appliquer des actions différentes selon le type de la valeur choisie.

### Exemples :
```javascript
// === TRAITER LES TYPES D'ACCOMMODATIONS ===
function getAccommodationFeatures(accommodationType) {
  let features = [];
  
  switch (accommodationType) {
    case "luxury":
      features.push("5-star amenities");
      features.push("Personal concierge");
      features.push("Space view suite");
      break;
    case "standard":
      features.push("Comfortable rooms");
      features.push("Wi-Fi included");
      features.push("Daily breakfast");
      break;
    case "budget":
      features.push("Basic rooms");
      features.push("Shared facilities");
      features.push("Eco-friendly");
      break;
    default:
      features.push("Unknown accommodation type");
  }
  
  return features;
}

console.log(getAccommodationFeatures("luxury"));
// ["5-star amenities", "Personal concierge", "Space view suite"]
```

### Sous sujet : Opérateur Ternaire 

### Définition :
L'opérateur ternaire est une syntaxe courte pour les conditions if/else simples. C'est le seul opérateur JavaScript qui prend trois opérandes : une condition, une expression si vrai, et une expression si faux. La syntaxe est concise et parfaite pour les assignations conditionnelles simples

### Syntaxe :
```javascript
condition ? expressionSiVrai : expressionSiFaux
// avec assignation
const resultat = condition ? valeur1 : valeur2;
```

### Cas d'Utilisation :
Assignations simples basées sur une condition.

Retourner des valeurs différentes en fonction d'une condition.

Appliquer des styles ou états conditionnels dans le DOM.

### Exemples :
```javascript
const message = `Status: ${isValid ? "Valid" : "Invalid"}`;
```
