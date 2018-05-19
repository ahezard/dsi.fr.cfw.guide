---
title: Installer Unlaunch
layout: single
sidebar:
  nav: "side"
---

Si vous avez une console non américaine vous devez avoir installé un exploit DSiWare antérieur pour pouvoir continuer.
{: .notice--info}

Unlaunch est actuellement en version beta, merci d'agir avec prudence.
{: .notice--info}

Unlaunch est un exploit du bootcode de la DSi qui permet d'installer HiyaCFW, un Custom Firmware DSi, sur votre console.

## Téléchargements
- La dernière version de [Unlaunch](http://problemkaputt.de/unlaunch.zip)
- La dernière version de [HBMenu](https://github.com/devkitPro/nds-hb-menu/releases/){:target="_blank"}
- La dernière version de [ugopwn](/assets/files/ugopwn.zip)
  - Seulement pour les consoles américaines.
- La dernière version de [twlnf](https://github.com/Jimmy-Z/twlnf/releases){:target="_blank"}
- La dernière version de [Python 3](https://www.python.org/downloads/){:target="_blank"}
- La dernière version de [DSi SRL Extractor](/assets/files/dsi_srl_extract.zip)

## Préparation de la carte SD

1. Installez Python 3 sur votre ordinateur
2. Ouvrez l'application "Paramètres de la console" de votre DSi
3. Sélectionnez **Gestion des données > Console > Flipnote Studio > Copier > Oui**
	- Si Gestion des données n'apparaît pas, ouvrez la Boutique Nintendo DSi puis fermez-la et réessayez ensuite.
4. Une fois ceci fait, éteignez votre console
5. Retirez la carte SD de votre console et insérez-la dans votre ordinateur
6. Copiez le contenu de l'archive `.zip` de ugopwn à la racine de votre carte SD
  - Seulement pour les consoles américaines
7. Copiez le contenu de l'archive `.7z` de twlnf à la racine de votre carte SD, ensuite renommez `twlnf.nds` en `boot.nds`
8. Copiez le contenu de l'archive `.zip` de DSi SRL Extractor dans un dossier de votre ordinateur
9. Sur votre ordinateur, ouvrez votre carte SD
10. Ouvrez le dossier /Private/DS/Title/
11. Copiez le fichier `.bin` dans le dossier contenant le DSi SRL Extractor
12. Executez le script console_id `.py` à l'intérieur du dossier
  - Ce script requiert [WINE](https://www.winehq.org/){:target="_blank"} sur les systèmes Mac/Linux/*nix
13. Quand demandé, appuyez sur Entrée
14. Copiez le nouveau fichier console_id `.txt` à la racine de votre carte SD
15. Ejectez votre carte SD et réinsérez-la dans votre console

## Faire une sauvegarde du NAND

1. Ouvrez Flipnote Studio
  - Assurez-vous que l'option *Calendrier au démarrage* est désactivée dans les options de Flipnote Studio
  - Si vous avez un autre exploit DSiWare installé alors ouvrez celui-ci et passez à l'étape 14
2. Sélectionnez **Voir une Flipnote > Carte SD > Choisir un dossier > User > ugopwn**
3. Cliquez sur la flipnote avec la moitié basse en rouge
4. Choisissez "Modifier"
5. Cliquez sur l'icone de grenouille dans le coin inférieur gauche
6. Cliquez sur l'icone de péliculle
7. Sélectionnez **Copier > Retour > Quitter**
8. Cliqez sur la seconde flipnote.
9. Cliquez sur l'icone de grenouille dans le coin inférieur gauche
10. Cliquez sur l'icone de péliculle
11. Cliquez sur l'icone de flèche vers la droite deux fois
  - Vous verrez une nouvelle page se créer
12. Cliquez sur le bouton Coller éxactement 122 fois.
13. Sélectionnez "Effacer" puis "Coller"
  - Ceci devrait lancer twlnf
14. Quand demandé, appuyez sur **A** pour créer une sauvegarde du NAND
  - Ceci peut prendre quelques minutes
  - Stockez cette sauvegarde dans un emplacement sûr, c'est une sauvegarde importante qui sera nécessaire plus tard pour l'installation de HiyaCFW
15. Appuyez sur **B** pour quitter twlnf
  - Votre console s'éteindra

## Installation

1. Insérez votre carte SD dans votre ordinateur
2. Copiez le ficher `BOOT.NDS` du dossier `hbmenu` situé dans l'archive `.tar.bz2` de HBMenu à la racine de votre carte SD
  - twlnf est actuellement votre `boot.nds`; pour le moment, renommez-le `boot.bak` ou bien `twlnf.nds`
3. Copiez le fichier `UNLAUNCH.DSI` de l'archive `.zip` de Unlaunch à la racine de votre carte SD
4. Renommez `UNLAUNCH.DSI` en `unlaunch.nds`
5. Ejectez votre carte SD et réinsérez-la dans votre console
6. Allumez votre DSi puis répétez les étapes 1 à 13 de **Faire une sauvegarde du NAND**
  - le HBMenu devrait se lancer
7. Sélectionnez `unlaunch.nds` et pressez le bouton **A**
  - l'installateur de Unlaunch devrait se lancer
8. Sélectionnez `INSTALL NOW` et pressez le bouton **A**
  - Si Unlaunch se bloque à `LOADING FAT`, veuillez consulter la [FAQ](/help/faq)
9. Une fois ceci terminé, sélectionnez `POWER DOWN` et pressez le bouton **A**
  - Votre console s'éteindra
10. Allumez votre console pour vérifer que Unlaunch s'est bien installé
  - Vous devriez voir brièvement l'image de démarrage de Unlaunch puis le menu DSi devrait se lancer, sans aucun son

Avec Unlaunch installé, votre système a maintenant une protection contre les "bricks", excepté si le fichier TMD du "launcher" est supprimé. Unlaunch possède des protections qui devraient empêcher ceci, de plus HiyaCFW utilise votre carte SD comme NAND, ainsi votre système est en théorie complètement protégé contre les "bricks".

[Installer HiyaCFW](/guide/installer-hiyacfw){: .btn .btn--light-outline}
{: style="text-align: center;"}