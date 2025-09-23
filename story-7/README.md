# Story 7 : Recompilation de l'APK

### EN TANT que développeur

### JE VEUX recompiler l'APK avec Apktool

### AFIN DE vérifier que la décompilation est réversible

### DoD : fichier livré + log de build

---

## Comment avons-nous procéder

Exécuter la commande suivante selon l'emplacement des fichiers et après avoir installer Apktool :

```
apktool b app_decode -o app_unsigned.apk 2>&1 | tee ~/Documents/Coding/CyberSecu/apktool_build.log
```

## Résultat

Vous trouverez dans le dossier `app_unsigned.apk` et `apktool_build.log`.