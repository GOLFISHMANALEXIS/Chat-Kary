# Chat-Kary
CHAT_APP for my crush Karyme using react and firebase with implementation in netlify, possible failures contact:
<p><a href="https://www.instagram.com/alexis._.vi/">@alexis._.vi</a></p>

## Nota:
*Cambiar la configuracion del SDK de la app

## Tecnologias
Este proyecto esta creado con:
* Node.js
* React.js
* Firebase

Dependencias:
```
$ npx create-react-app (name)
$ cd (name)
$ npm install firebase react-firebase-hooks
$ npm run build
```
Datos de coleccion:
```
$ iniciar una coleccion
$ nombre:
$ messages
$ id automatico
$ Campo = text-string("x")
$ Agregar campo:
$ createdAt con tipo "timestamp"
$ fecha al dia de creacion 
```
Reglas de database:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
  
    match /{document=**} {
      allow read, write: if false;
    }
    
    match /messages/{docId}{
      allow read: if request.auth.uid != null;
      allow create: if canCreateMessage();
    }
    
    function canCreateMessage(){
     let isSignedIn = request.auth.uid != null;
     let isOwner = request.auth.uid == request.resource.data.uid;
     
     let isNotBanned = exists(
     /databases/$(database)/documents/banned/$(request.auth.uid)
     )== false;
     
     return isSignedIn && isOwner && isNotBanned;
     
    }
    
  }
}
```
Si quieres clonar el repositorio:
```
$ wind+r
$ cmd+enter
$ cd desktop
$ git clone https://github.com/GOLFISHMANALEXIS/Chat-Kary.git
```



