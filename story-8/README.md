# Story 8 : Signature de l'APK

### EN TANT que testeur

### JE VEUX signer l'APK recompilé

### AFIN DE pouvoir l'installer sur un émulateur ou terminal

### DoD : rebuilt_signed.apk livré + preuve apksigner verify

---

## Comment avons-nous procéder

On a dans un premier temps générer une clé privée et un fichier keystore pour la signature :

```
keytool -genkey -v -keystore app_keystore.jks -keyalg RSA -keysize 2048
```

On répond ensuite aux prompts de l'outil (mot de passes, les informations du certificat tel que le nom de l'organisation ou sa localisation).

Enfin on signe l'application :

```
apksigner sign -ks app_keystore.jks app_unsigned.apk
```

## Résultat

Vous retrouverez dans ce dossier les fichiers `rebuilt_signed.apk` et deux images prouvant la signature de l'application.