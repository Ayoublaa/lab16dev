````md id="lab16services"
# LAB 16 — Maîtriser les Services Android

![Android](https://img.shields.io/badge/Platform-Android-green)
![Java](https://img.shields.io/badge/Language-Java-orange)
![Service](https://img.shields.io/badge/Component-Services-blue)

## 📌 Description

Ce laboratoire présente la création d’un chronomètre Android utilisant :

- Foreground Service
- Bound Service
- Notifications persistantes
- Communication Activity ↔ Service

---

# 🎯 Objectifs

- comprendre les Services Android ;
- utiliser un Foreground Service ;
- afficher une notification persistante ;
- démarrer et arrêter un service ;
- communiquer avec l’Activity.

---

# ⚙️ Prérequis

- Android Studio
- Java
- Android SDK

---

# 🚀 Étape 1 — Création du Projet

Créer :

```text
Empty Activity
Language: Java
````

---

# 📂 Étape 2 — Créer le Service

Exemple :

```java id="t9q3vw"
public class TimerService extends Service {

}
```

---

# 🔥 Foreground Service

Exemple :

```java id="m7x2pk"
startForeground(
1,
notification
);
```

---

# 🔗 Bound Service

Créer Binder :

```java id="q4v8ls"
public class LocalBinder extends Binder {

    TimerService getService() {

        return TimerService.this;
    }
}
```

---

# 📱 Étape 3 — Manifest

Ajouter :

```xml id="x1r5mn"
<service
    android:name=".TimerService"
    android:exported="false"/>
```

---

# 🔔 Étape 4 — Permission Notification

```xml id="u6p2qt"
<uses-permission
android:name="android.permission.POST_NOTIFICATIONS"/>
```

---

# 🖥 Étape 5 — MainActivity

Démarrer Service :

```java id="f8m4rw"
Intent intent =
new Intent(this, TimerService.class);

startService(intent);
```

---

# ⏹ Arrêter Service

```java id="p3x7vn"
stopService(intent);
```

---

# 🎨 Étape 6 — Layout

Ajouter :

* Button Start
* Button Stop
* TextView Timer

---

# ▶️ Étape 7 — Exécution

Résultat attendu :

* chronomètre actif ;
* notification visible ;
* service fonctionne en arrière-plan.

---
<img width="181" height="328" alt="image" src="https://github.com/user-attachments/assets/c4c526b2-7f7a-44dd-9ea7-45857568d7f3" />


# 📚 Concepts Appris

* Foreground Service
* Bound Service
* Notification Android
* Service Lifecycle
* START_STICKY

---

# ⚠️ Bonnes Pratiques

* utiliser Foreground Service ;
* éviter consommation batterie ;
* arrêter le service correctement ;
* limiter tâches inutiles.

---

# 👨‍💻 Auteur

Ayoub Laafar — EMSI Marrakech

```
```
