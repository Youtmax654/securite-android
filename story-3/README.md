# Story 3 : Extraction de fichiers

### EN TANT que reverse-engineer

### JE VEUX extraire classes.dex / Manifest.xml de l'APK

### AFIN DE préparer une décompilation

### DoD fichiers livré avec hash SHA256

---

## Comment avons-nous procéder

Exécuter la commande suivante selon l'emplacement des fichiers :

```
unzip app.apk classes.dex AndroidManifest.xml -d app
```

## Résultat

Vous trouverez dans le dossier les fichiers `classes.dex` et `AndroidManifest.xml`.