## Sujet : Manipulation du DOM

### Sous sujet : Sélection d'Éléments 

### Définition :
JavaScript offre plusieurs méthodes pour sélectionner des éléments HTML dans le DOM, dont les plus courantes sont :

getElementById : sélectionne un élément unique par son ID (chaîne unique dans la page).​

querySelector : retourne le premier élément correspondant à n'importe quel sélecteur CSS valide (ID, classe, balise, attribut, combinaison).​

querySelectorAll : retourne une NodeList statique de tous les éléments correspondant à un sélecteur CSS.

### Syntaxe :
```javascript
const element = document.getElementById("idDeLElement");
const element = document.querySelector("sélecteurCSS");
const element = document.querySelector("sélecteurCSS");
const element = document.querySelectorAll("sélecteurCSS");

```

### Cas d'Utilisation :
getElementById est ultra-rapide, mais limité à un ID précis (donc à un seul élément unique).​

querySelector : pour le premier élément d’une classe, d’un type ou d’un set d’attributs, ou d’une structure combinée.

querySelectorAll sert à travailler avec l’ensemble des éléments matches (ajouter une classe à tous les boutons .btn). 

### Exemples :
```javascript
// Récupérer des références clés
const bookingForm = document.getElementById("bookingForm");
const destinationSelect = document.querySelector("#destination");
const allPassengerBlocks = document.querySelectorAll(".passenger-block");
const addBtns = document.querySelectorAll(".add-passenger-btn");
```


### Sous sujet : Gestion des Événements

### Définition :
La méthode addEventListener() permet d’attacher une fonction appelée gestionnaire d’événement à un élément du DOM. Cette fonction est déclenchée quand l’événement spécifié (clic, soumission, changement, saisie…) se produit sur cet élément.​
C’est la méthode recommandée pour gérer les événements car elle permet d’ajouter plusieurs gestionnaires au même élément sans écraser les précédents.

### Syntaxe :
```javascript
element.addEventListener("typeDévent", fonctionGestionnaire, options);
```

### Cas d'Utilisation :
Écouter les clics sur les boutons (ajouter, supprimer, sélectionner)

Valider les formulaires avant soumission (intercepter submit)

Valider les champs en temps réel lors de la saisie (input)

Mettre à jour dynamiquement l’interface lors d’un changement de sélection (change)

Empêcher le comportement par défaut (ex : empêcher le rechargement au submit)

Améliorer l’UX avec focus, hover, et autres interactions utilisateurs

### Exemples :
```javascript
destinationSelect.addEventListener("change", () => {
  selectedDestination = getSelectedDestination();
  updateAccommodationOptions();
  updateTotalPrice();
});

```

### Sous sujet : Création/Modification d'Éléments

### Définition :
Ces méthodes sont utilisées pour créer, insérer et modifier dynamiquement des éléments HTML dans le DOM.

createElement crée un nouvel élément HTML.

appendChild ajoute un élément enfant dans un élément parent existant.

innerHTML permet d’insérer ou modifier le contenu HTML d’un élément.

### Syntaxe :
```javascript
// Créer un nouvel élément
const nouveauDiv = document.createElement("div");

// Ajouter un enfant à un élément parent
parentElement.appendChild(nouveauDiv);

// Modifier ou ajouter du contenu HTML
parentElement.innerHTML = "<p>Contenu HTML</p>";
```

### Cas d'Utilisation :
Ajouter dynamiquement des sections au formulaire (exemple : ajout de passagers).

Modifier ou rafraîchir des parties de page sans recharger.

Construire une interface utilisateur interactive, réactive aux actions utilisateur.

Insérer rapidement du contenu HTML formaté (avec innerHTML).

### Exemples :
```javascript
// Ajouter un nouvel élément simple sans innerHTML
const label = document.createElement("label");
const input = document.createElement("input");
input.type = "text";
input.name = "newField";
label.textContent = "Nouveau champ : ";
label.appendChild(input);
passengerContainer.appendChild(label);
```
