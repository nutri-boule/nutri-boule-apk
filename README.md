# nutri-boule — distribution

Ce dépôt ne contient **aucun code source** : il ne sert qu'a heberger l'APK de
l'application Android [nutri-boule](https://github.com/nutri-boule/nutri-boule),
dont le code est reste prive.

## Pourquoi deux depots

L'application verifie les mises a jour en telechargeant l'APK a une adresse
HTTPS. Un fichier de release situe dans un depot prive renvoie une erreur
404 a toute requete anonyme — le telephone n'envoie aucun jeton. L'APK doit
donc etre servi depuis un depot public, ce que fait celui-ci.

## Recuperer l'APK d'une version

L'onglet **Reglages** de l'application demande l'adresse du fichier lui-meme,
celle de l'asset, et non celle de la page de la release :

    https://github.com/nutri-boule/nutri-boule-apk/releases/download/v<version>/nutri-boule-<version>.apk

## Signature

Ces APK sont signes avec une **cle de debug** (CN=Android Debug). Cela permet
de mettre a jour une application deja installee sans perte de donnees, puisque
la cle est la meme sur toutes les versions. L'application refuse par ailleurs
tout APK signe avec un autre certificat.

Une cle de signature propre sera necessaire pour une publication reelle.