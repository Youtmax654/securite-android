***

```
<string name="google_api_key">AIzaSyBTgztvImsUfMWDa41PCrDWAj7dmyIDhUg</string>
```

La clé peut être utilisé par n'importe qui pour effectuer des actions avec l'API Google

***

```
<string name="PUSHWOOSH_APPID">DDF11-D1BF9</string>
```

ID de l'application pour le service PushWoosh (service de notification)

***

```
<string name="firebase_database_url">https://application-client-nickel.firebaseio.com</string>
```

Peut permettre à l'attaquant d'accéder à la base de données Firebase.

La base de données n'est pas accessible par navigateur.

***

```
<string name="ACCOUNT_ENDPOINT">https://api.nickel.eu/customer-banking-api</string>

<string name="CUSTOMER_AUTHENTICATION_ENDPOINT">https://api.nickel.eu/customer-authentication-api</string>

<string name="PERSONAL_SPACE_API_ENDPOINT">https://api.nickel.eu/personal-space-api</string>
```

Ces URL pointent vers les services backend de l'application pour les opérations bancaires, l'authentification des clients et la gestions des espaces personnels.

Ça laisse des points d'entrées aux attaquants.

