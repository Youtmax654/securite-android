# Story 2 : Analyse automatisée avec MobSF

### EN TANT que analyste

### JE VEUX scanner l'APK avec MobSF

### AFIN DE identifier rapidement métadonnées et vulnérabilités

### DoD mobSf_report.pdf + résumé des vulnérabilités

---

## Comment avons-nous procéder

Nous avons lancer le logiciel MobSF via Docker :

```
docker pull opensecurity/mobile-security-framework-mobsf:latest

docker run -it --rm -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest

# Default username and password: mobsf/mobsf
```

## Résultat

Vous trouverez dans le dossier le fichier `mobSF_report.pdf` contenant le rapport de l'analyse du logiciel.

## Résumé

Dans ce rapport, l'application a une note de sécurité de 49/100.

On voit des vulnérabilités notamment sur les permissions, où il est demandé de pouvoir lire les contacts de l'utilisateur, et d'écrire sur les stockages externes, ce qui n'est pas normal pour ce type d'application.

L'application utilise le "ClearText" qui est dérangeant sur les points de confidentialité et d'intégrité des données.

L'application utilise une méthode d'encryptage (CBC avec PKCS5 / PKCS7) qui est vulnérable aux attaques "padding oracle".

Enfin, l'application peut être installé sur une version d'Android qui est vulnérable (Android 4.4)

## Source

- https://github.com/MobSF/Mobile-Security-Framework-MobSF?tab=readme-ov-file
- https://mobsf.github.io/docs/#/running_mobsf_docker