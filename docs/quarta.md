![quarta exericse](quarta.png)

[Lien repository ](https://github.com/elhayanich/prairie_quarta)

# Fichier Json
```json
[
    "Chaymae",
    "Connie",
    "Manal",
    "Mariam",
    "Harold",
    "Colas",
    "Mathieu",
    "Mattias",
    "Bruno",
    "Léo",
    "Karolan",
    "Sofian",
    "Avriska",
    "Ioana"
]

# Code en Python :

```python
import json
import random

def groupes(k):
    names = json.load(open("apprenants.json"))  
    random.shuffle(names)  
    return [names[i:i + k] for i in range(0, len(names), k)]  

# Exemple avec k = 2
for i, Team in enumerate(groupes(2), 1):
    print(f"Team {i}: {Team}")

# Code en JavaScript :

```javascript
const apprenants = [
    "Chaymae", "Connie", "Manal", "Mariam", "Harold",
    "Colas", "Mathieu", "Mattias", "Bruno", "Léo",
    "Karolan", "Sofian", "Avriska", "Ioana"
];

function shuffle(array) {
    const newArray = [...array];
    const length = newArray.length;
    for (let i = 0; i < length; i++) {
        const randomPosition = Math.floor((newArray.length - i) * Math.random());
        const randomItem = newArray.splice(randomPosition, 1);
        newArray.push(...randomItem);
    }
    return newArray;
}

const array = ["a", "b", "c", "d", "f", "g"];
const newArray = shuffle(array);
console.log(newArray);

function groupes(k) {
    shuffle(apprenants); 
    const result = [];
    
    for (let i = 0; i < apprenants.length; i += k) {
        result.push(apprenants.slice(i, i + k)); 
    }

    return result; 
}

const k = 5; 
const groupesResultats = groupes(k);
console.log(groupesResultats);

# Résultats obtenus  :

Le programme va créer des groupes de manière aléatoire en fonction de la valeur définie dans K 

**Résultats obtenus en Python si `K=2`** 

![Python result](pt2.png)

**Résultats obtenus en JavaScript si `K=5`**

![javascript Result ](js5.png)

