# Marie — application Android

Application Android de [Marie](https://marie-ai.vercel.app) : le site ouvert en plein écran
(Trusted Web Activity, via Chrome). Compte, séances, voix et achats viennent du site, donc chaque
mise en ligne du site met l'application à jour sans nouvel APK.

Le code du site est dans le dépôt `Marie` ; ce dépôt ne contient que l'application.

## Fabriquer l'APK

Le workflow « APK Android » (`.github/workflows/android-apk.yml`) construit l'APK à chaque modification
de `android/`, ou à la demande (onglet Actions → APK Android → Run workflow). L'APK sort **non signé** et
est déposé sur la branche `android-apk` et en artefact. La clé de signature n'est jamais dans ce dépôt
(il est public) : l'APK est signé à part, avec la clé dont l'empreinte SHA-256 figure dans
`public/.well-known/assetlinks.json` du site.

## Installer sur un téléphone

Ouvrir `marie.apk` sur le téléphone, autoriser l'installation depuis cette source, puis Installer.
Chrome doit être présent sur le téléphone.

## Réglages

- Identifiant : `app.vercel.marie_ai.twa`
- Page d'ouverture : `https://marie-ai.vercel.app/espace`
- Pour une version Google Play, ouvrir `/espace?source=android-app` : le site masque alors l'achat
  (règle de paiement de Google Play).
