# POLITIQUE DE SÉCURITÉ MOBILE

## 1. OBJECTIF ET PÉRIMÈTRE

Cette politique définit les exigences de sécurité pour toutes les applications mobiles de l'organisation, basée sur les standards OWASP Mobile Top 10 et les stories précédentes.

---

## 2. RÈGLES DE DÉVELOPPEMENT SÉCURISÉ

### 2.1 🔴 INTERDICTIONS CRITIQUES
- **Jamais de secrets dans le code** : Clés API, mots de passe, tokens
- **Jamais de ClearText** : HTTPS obligatoire partout
- **Jamais d'injection SQL** : Requêtes préparées uniquement

```xml
<!-- ❌ INTERDIT -->
<string name="api_key">AIzaSyBTgztvImsUfMWDa41PCrDWAj7dmyIDhUg</string>
<application android:usesCleartextTraffic="true">

<!-- ✅ OBLIGATOIRE -->
<application android:usesCleartextTraffic="false">
```

### 2.2 ✅ EXIGENCES OBLIGATOIRES

#### Chiffrement
- **AES-GCM uniquement** (abandonner CBC/PKCS7)
- **RSA 2048 bits minimum**
- **SHA-256 ou supérieur**

#### Base de données
```java
// ✅ Toujours utiliser des requêtes préparées
String query = "SELECT * FROM users WHERE id=?";
Cursor cursor = db.rawQuery(query, new String[]{userId});
```

#### Permissions
- **Principe du moindre privilège**
- **Justification obligatoire** pour chaque permission
- **Éviter** : READ_CONTACTS, WRITE_EXTERNAL_STORAGE

#### Support Android
- **minSdkVersion ≥ 23** (Android 6.0+)
- **targetSdkVersion** = dernière version stable

---

## 3. TESTS ET VALIDATION

### 3.1 Critères de Validation
- **Score MobSF ≥ 80/100** : Obligatoire
- **Zéro vulnérabilité critique** : Non négociable  
- **Max 2 vulnérabilités élevées** : Avec plan de correction

### 3.2 Outils Obligatoires
- **MobSF** : Scan automatisé
- **Tests statiques** : Analyse du code source
- **Tests dynamiques** : Validation fonctionnelle

---

## 4. ARCHITECTURE SÉCURISÉE

### 4.1 Séparation des Couches
- **Mobile** : Interface + validation locale
- **API Gateway** : Authentification + autorisation
- **Backend** : Logique métier sécurisée
- **Database** : Stockage chiffré

### 4.2 Authentification
- **OAuth 2.0 + PKCE** recommandé
- **JWT avec rotation** pour les tokens
- **Timeout de session** configuré

---

## 5. GESTION DES INCIDENTS

### 5.1 Temps de Réponse
- **Critique** : 1 heure
- **Élevé** : 4 heures  
- **Moyen** : 24 heures

### 5.2 Actions Automatiques
- **Vulnérabilité critique** → Blocage déploiement
- **Score MobSF < 80** → Retour développement
- **Secrets exposés** → Révocation immédiate

---

## 6. CHECK-LIST DE VALIDATION

Avant chaque déploiement :
- [ ] Aucun secret dans le code source
- [ ] ClearText désactivé (usesCleartextTraffic="false")
- [ ] Chiffrement AES-GCM uniquement
- [ ] Requêtes SQL préparées
- [ ] Permissions minimales justifiées
- [ ] minSdkVersion ≥ 23
- [ ] Score MobSF ≥ 80/100
- [ ] Tests de sécurité validés
