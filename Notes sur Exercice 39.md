# Résumé des difficultés rencontrées pendant le travail sur cet exercice

## Code écrit pour résoudre l'énigme de l'exercice 39 :

```javascript
let lancement = function(message) {
  var reponses = [];
  let i = 0;
  let reponse = null;
  while (reponse == null || reponse == '' || isNaN(reponse)) {
    reponse = prompt(`Veuillez s'il vous plaît entrer un nombre ou un chiffre (uniquement) :`);
  };
  while (reponse != null && reponse != '' && parseFloat(reponse)) {
    reponses[i] = parseFloat(reponse);
    i++;
    reponse = prompt(message);
  };
  alert(`Vous avez saisi les nombres ou chiffres suivants : ${reponses.join(' ')}.`)
  if (reponses['length'] >= 1) {
    let sum = 0;
    if (reponses['length'] == 1) {
      sum = reponses;
    } else {
      for (let j=1;j<reponses['length'];j++) {
        sum = reponses[0] += reponses[j];
      };
    };
    let result = sum/reponses['length']
    alert(`La moyenne des nombres saisis est : ${result}.`);
  };
};

lancement(`Entrez à nouveau un nombre, ou cliquez sur OK ou Annuler pour lancer l'opération de calcul de la moyenne :`);
```

Voici l'exercice sur lequel j'ai le plus galéré parmi tous les exercices qui ont été proposés pendant la formation, à ce jour.

### Les problèmes rencontrés dans la résolution de cet exercice

J'ai eu du mal à faire en sorte d'obliger l'utilisateur à entrer un nombre et rien d'autre, avant de pouvoir rentrer dans le corps de la fonction. J'ai résolu ce souci en initiant la variable reponse avec la valeur <code>null</code>.

J'ai un peu galérer pour la boucle for, également, car j'utilisais une condition de test étrange avec <code>saisies[i]</code>, en voulant me baser sur ce que Marc avait fait à l'exercice 27. Cela dit, je n'avais pas compris que cela n'était pas possible vu que je n'utilisais pas la valeur j dans le code exécuté par la boucle <code>for</code>. En changeant le test de <code>for</code> en <code>j<reponses['length']</code>, la boucle faisait ce que je voulais, à savoir additionner la valeur à l'index 0 du tableau reponses avec toutes les valeurs subséquentes, et stocker le résultat dans la variable sum qui avait été déclarée plus haut.

### Question : aurais-je pu améliorer ce code ? Si oui, comment ?

```javascript



```