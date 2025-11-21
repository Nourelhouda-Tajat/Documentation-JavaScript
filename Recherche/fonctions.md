## Sujet : Fonctions

### Sous sujet : Déclarations de fonction 

### Définition :
Une déclaration de fonction est une façon de définir une fonction réutilisable avec le mot-clé function. Elle est hoisted au début du scope, ce qui signifie qu'elle peut être appelée avant sa déclaration dans le code.

### Syntaxe :
```javascript
function nomDeLaFonction(parametres) {
  // Corps de la fonction
  return resultat;
}
```

### Cas d'Utilisation :
Définir des fonctions réutilisables et nommées pour plus de clarté.

Lorsque la fonction doit être appelée avant sa déclaration dans le code (grâce au hoisting).

Pour des opérations complexes qui nécessitent une logique bien structurée.

### Exemples :
```javascript
// Fonction pour sauvegarder une réservation dans localStorage
function saveBooking(bookingData) {
  let bookings = JSON.parse(localStorage.getItem("bookings") || "[]");
  bookings.push(bookingData);
  localStorage.setItem("bookings", JSON.stringify(bookings));
}

// Appel
saveBooking(bookingData);
```


### Sous sujet : Expressions de fonction

### Définition :
Une expression de fonction est une fonction assignée à une variable. Elle peut être nommée ou anonyme. Les expressions de fonction ne sont pas hissées, donc elles doivent être déclarées avant d'être utilisées.

### Syntaxe :
```javascript
const nomFonction = function(param1, param2) {
    // corps de la fonction
    return résultat;
};

```

### Cas d'Utilisation :
Assigner une fonction à une variable pour une utilisation ultérieure.

Passer une fonction en argument à une autre fonction (callbacks).

Créer des fonctions privées ou locales dans une portée limitée.

### Exemples :
```javascript
// Fonction pour calculer le prix total (expression de fonction)
const updateTotalPrice = function() {
  if (!selectedDestination || !selectedAccommodation) {
    priceBox.textContent = "$0";
    return;
  }

  const days = 7;
  const total = 
    selectedDestination.price + 
    days * selectedAccommodation.pricePerDay * passengerCount;
  priceBox.textContent = "$" + total.toLocaleString();
};

// Appel
updateTotalPrice();

```

### Sous sujet : Fonctions fléchées 

### Définition :
Les fonctions fléchées sont une syntaxe concise introduite avec ES6 (2015). Elles utilisent la notation => et héritent du contexte this de leur parent.

### Syntaxe :
```javascript
const nomFonction = (param1, param2) => {
    return résultat;
};
```

### Cas d'Utilisation :
Utiliser dans les callbacks d'événements (.addEventListener, .map(), .filter(), etc.).

Pour une syntaxe plus lisible et concise, notamment dans les itérations.

Lorsqu'on souhaite préserver le contexte this du scope parent.

### Exemples :
```javascript
// Arrow function pour charger les destinations via fetch
fetch("destinations.json")
  .then((res) => res.json())
  .then((data) => {
    destinationsData = data.destinations;
    destinationsData.forEach((dest) => {
      const option = document.createElement("option");
      option.value = dest.id;
      option.textContent = dest.name + " - $" + dest.price.toLocaleString();
      destinationSelect.appendChild(option);
    });
  });
```
