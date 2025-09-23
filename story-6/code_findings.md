```
KeyStore keyStoreAndLoad = getKeyStoreAndLoad();
if (!keyStoreAndLoad.containsAlias(defaultServiceIfEmpty)) {
    KeyGenParameterSpec keyGenParameterSpecBuild = new KeyGenParameterSpec.Builder(defaultServiceIfEmpty, 3).setBlockModes("CBC").setEncryptionPaddings("PKCS7Padding").setRandomizedEncryptionRequired(true).setKeySize(256).build();
    KeyGenerator keyGenerator = KeyGenerator.getInstance("AES", "AndroidKeyStore");
    keyGenerator.init(keyGenParameterSpecBuild);
    keyGenerator.generateKey();
}
```

Ce code dans `/com/oblador/keychain/cipherStorage/CipherStorageKeystoreAESCBC.java` utilise une méthode d'encryptage qui est vulnérable aux attaques de type "padding oracle"

***

```
private com.pushwoosh.inapp.e.b.b a(String str, SQLiteDatabase sQLiteDatabase) {
    Cursor cursorRawQuery = sQLiteDatabase.rawQuery("Select * from inApps where code='" + str + "';", null);
    try {
        if (cursorRawQuery.moveToFirst()) {
            return a(cursorRawQuery);
        }
        return null;
    } finally {
        cursorRawQuery.close();
    }
}
```

Ce code fait des requêtes SQL sans échappé le paramètre, ça rend le code vulnérable aux injections SQL.

***

