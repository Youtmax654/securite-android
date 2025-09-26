# Story 9 : Vérification Firebase

### EN TANT que pentesteur

### JE VEUX tester l'accès publique à une éventuelle base Firebase

### AFIN DE évaluer le risque de fuite de données

### DoD : firebase_check.md + capture de la réponse

---

## Comment avons-nous procéder

Avec l'url trouvé dans le strings de la story 5, exécuter la commande suivante :

```
curl -s https://application-client-nickel.firebaseio.com/.json
```

## Résultat

Vous trouverez dans le fichier `firebase_check.md` le détail de la réponse.