# Story 6 : Analyse de code

### EN TANT que ingénieur sécurité

### JE VEUX décompiler le bytecode

### AFIN DE trouver vulnérabilités logiques ou mauvaies pratiques

### DoD : code_findings.md avec explication pour chaque extrait.

---

## Comment avons-nous procéder

On a décompiler le fichier `classes.dex` récupéré dans la story 3 en utilisant Jadx :

```
jadx -d out classes.dex
```

## Résultat

Vous trouverez le fichier `code_findings.md` dans ce dossier.