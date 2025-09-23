# Story 1 : Téléchargement et vérification de l'APK

### EN TANT que testeur

### JE VEUX recevoir l'APK vulnérable déjà fourni par le PO

### AFIN DE travailler sur une base commune

### DoD Chaque étudiant vérifie le hash avec sha256sum app.apk et documente le résultat.

---

## Mac / Linux

Pour récupérer le hash du fichier app.apk, il faut lancer une commande dans son terminal :

```
sah256sum app.apk
```

## Windows

Pour Windows, la commande est le suivant :

```
Get-FileHash app.apk
```

## Résultat

Nous avons récupérer comme hash :

`f01f08c8b6e2fe4612e81bc7e3a3ba9440dad0d7a962f4e67640390dd721d528`

## Source

https://next.ink/1188/comment-verifier-integrite-dun-fichier-via-son-empreinte-sha256/