# Reverse-Engineering-de-Uncrackable-Level-2
Ce laboratoire porte sur le reverse engineering de l'application OWASP UnCrackable Level 2, une application Android intentionnellement vulnérable conçue à des fins pédagogiques. L'objectif est d'analyser le code natif de l'application afin d'en extraire le secret protégé, en combinant plusieurs outils d'analyse statique.

Objectifs du laboratoire

Décompiler l'APK avec JADX pour identifier les composants natifs.
Localiser et extraire la bibliothèque native libfoo.so.
Analyser le binaire natif avec Ghidra pour en décompiler le code.
Identifier la logique de vérification du code secret.
Tester le code extrait directement sur l'application.


Réalisation
Étape 1 — Analyse de l'APK avec JADX et localisation de libfoo.so
<img width="707" height="127" alt="Capture d&#39;écran 2026-05-08 215022" src="https://github.com/user-attachments/assets/590df5d2-dc38-4493-94e1-fbcd7e0f142a" />


ouvre l'APK dans JADX et navigue dans l'arborescence des ressources pour localiser la bibliothèque native libfoo.so, qui contient la logique de vérification du secret.


Étape 2 — Décompilation de libfoo.so avec Ghidra
<img width="1919" height="1079" alt="Ghidra - décompilation libfoo.so" src="https://github.com/user-attachments/assets/4023a0f0-0fbd-4f0a-ad65-dfab858688e3" />

Importe libfoo.so dans Ghidra, procède à l'analyse du binaire et extrait le code décompilé. L'examen des fonctions permet d'identifier la routine responsable de la comparaison du code secret.


Étape 3 — Test du code secret extrait sur l'application
<img width="412" height="843" alt="Test du code - tentative 1" src="https://github.com/user-attachments/assets/d9d49da9-2c1e-4a64-8b56-46bc9e2467ee" />
<img width="412" height="850" alt="Test du code - résultat" src="https://github.com/user-attachments/assets/bf139f7f-efc8-4f95-a7ee-4b981cd1a4b0" />

saisit le code secret obtenu par l'analyse statique directement dans l'application. Le résultat confirme que le reverse engineering a permis d'identifier correctement la valeur attendue..
