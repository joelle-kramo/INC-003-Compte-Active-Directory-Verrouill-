# INC-003 — Compte Active Directory verrouillé

## Contexte
Une utilisateur contacte le support car il ne parvient plus à ouvrir sa session Windows sur son poste de travail.

## Symptômes
* Échec de connexion à Windows
* Message indiquant que le compte est verrouillé
* Accès impossible aux ressources du domaine
* Demandes répétées du mot de passe

## Diagnostic

### 1. Vérification du compte utilisateur

Ouverture de la console :
``` cmd
dsa.msc
```
Navigation :
``` text
Active Directory Users and Computers
```
**Observation :**
* Compte utilisateur marqué comme verrouillé

## 2. Vérification des tentatives d'authentification

Contrôle des événements de sécurité sur le contrôleur de domaine :
```cmd
eventvmr.msc
```
Journal :
```text
Windows Logs > Security
```

**Observation :**
* Plusieurs échecs d'authentification détectés
* Verrouillage déclenché après dépassement du seuil autorisé

## 3. Recherche de la source du verrouillage

Vérification : 
* Poste utilisateur
* Smartphone synchronisé avec Outlook
* Lecteurs réseau enregistreés
* Applications utilisant les anciens identifiants

**Observation :**

* Ancien mot de passe encore enregistré sur un appareil mobile

## Cause probable

* Multiples saisies incorrectes du mot de passe
* Mot de passe récemment modifié
* Application ou équipement utilisant des identifiants obsolètes

## Résolution

Déverrouillage du compte dans Active Directory :

```text
Propriétés utilisateur
-> Onglet Compte
-> Déverouiller le compte
```

Mise à jour des identifiants :

* Smartphone reconfiguré
* Anciennes informations d'authentification supprimés

## Résultat

* Connexion Windows rétablie
* Accès aux ressources du domaine fonctionnel
* Aucun nouveau verrouillage constaté

## Compétences démontrées

* Administration Activce Directory
* Gestion des comptes utilisateurs
* Analyse des journaux Windows
* Diagnostic d'authentification
* Support utilisateur niveau 1 / niveau 2
* Sécurité des accès
