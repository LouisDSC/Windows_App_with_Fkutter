# <h1 align="center">🔭&nbsp;Application Windows avec Flutter</h1>

## ⚡&nbsp;Mise à jour de FLutter
Si vous n'avez pas encore mis à jour votre version de Flutter, rendez-vous sur la page de publication de  [Flutter](https://docs.flutter.dev/development/tools/sdk/releases?tab=windows/), téléchargez la version la plus récente pour votre système d'exploitation et installez-la.
Ou utilisez simplement l'outil de ligne de commande de votre choix et exécutez
```CMD
  flutter upgrade
```
Pour le système d'exploitation windows, vous devrier avoir un résultat dans ce sens
```CMD
Flutter is already up to date on channel stable
Flutter 2.10.2 • channel stable • https://github.com/flutter/flutter.git
Framework • revision 097d3313d8 (9 days ago) • 2022-02-18 19:33:08 -0600
Engine • revision a83ed0e5e3
Tools • Dart 2.16.1 • DevTools 2.9.2
``` 
Cela fera tout le travail pour vous. Bien sûr, cela n'est possible que si vous avez déjà installé une ancienne version du SDK Flutter sur votre système.
Si vous ne connaissez pas votre configuration actuelle, exécutez
```CMD
  flutter doctor
``` 
Pour le système d'exploitation windows, vous devrier avoir un résultat dans ce sens
```CMD
[√] Flutter (Channel stable, 2.10.2, on Microsoft Windows [version 10.0.19043.1466], locale fr-FR)
[!] Android toolchain - develop for Android devices (Android SDK version 32.1.0-rc1)
    X No Java Development Kit (JDK) found; You must have the environment variable JAVA_HOME set and the java binary in
      your PATH. You can download the JDK from https://www.oracle.com/technetwork/java/javase/downloads/.
[√] Chrome - develop for the web
[√] Visual Studio - develop for Windows (Visual Studio Community 2022 17.1.0)
[!] Android Studio (not installed)
[√] VS Code (version 1.64.2)
[√] Connected device (3 available)
[√] HTTP Host Availability

! Doctor found issues in 2 categories.
``` 
## ⚙️&nbsp;Construire des exécutables
Pour créer un fichier exécutable pour votre projet Flutter, vous devez exécuter la commande
```CMD
  flutter build windows
``` 
 Les fichiers créés, y compris l'application, seront placés dans le sous-dossier ( build\windows\runner\Release ). \
 L'application n'est pas autonome, ce qui signifie qu'elle dépend du dossier de données et du fichier DLL. Si vous souhaitez distribuer l'application, assurez-vous d'inclure également les données requises.
 
 ## ⚙️&nbsp;Création de packages MSIX
 Les packages MSIX fournissent des routines d'installation et de désinstallation et contiennent tout le nécessaire pour exécuter l'application. \
 Par conséquent, ils sont bien mieux adaptés si vous souhaitez distribuer votre application. La création de packages MSIX nécessite  [le package MSIX](https://pub.dev/packages/msix/) . \
 Vous pouvez l'ajouter à votre projet en exécutant la commande 
 ```CMD
  flutter pub add --dev msix
``` 
ou en ajoutant manuellement la référence à votre fichier pubspec.yaml.

Pour créer le package, créez d'abord l'exécutable, puis le package à l'aide de ces commandes
```CMD
  flutter build windows 
  flutter pub run msix:create
``` 
Le package créé est stocké dans le même sous-dossier que l'exécutable ( build\windows\runner\Release )
 
