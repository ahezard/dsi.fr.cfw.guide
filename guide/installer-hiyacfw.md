---
title: Installer HiyaCFW
layout: single
sidebar:
  nav: "side"
---

Si vous avez une console non américaine vous devez avoir installé un exploit DSiWare antérieur pour pouvoir continuer.
{: .notice--info}

Vous aurez besoin d'installer [Unlaunch](/guide/installing-unlaunch/) avant de continuer.
{: .notice--info}

Ne faites pas de mise à jour système après l'installation de HiyaCFW, ceci retirerait les patchs mis en place.
{: .notice--danger}

HiyaCFW est un custom firmware pour DSi, une fois installé il permet de:
- Démarrer le système depuis la carte SD
- Installer des homebrews directement sur le menu DSi
- Lancer les flashcarts bloquées sur les derniers firmwares

## Pré-Requis
- La dernière version de [Python 3](https://www.python.org/downloads/){:target="_blank"}
  - Vous devriez déjà avoir ceci d'installé (voir Installer Unlaunch)
- Une carte SD de 2Go ou moins, ou alors une carte SD de plus grosse taille mais partitionnée pour faire moins de 2Go
- La dernière version de [twlnf](https://github.com/Jimmy-Z/twlnf/releases){:target="_blank"}
- La dernière version de [HiyaCFW](https://github.com/Robz8/hiyaCFW/releases){:target="_blank"}
- La dernière version de [ugopwn](/assets/files/ugopwn.zip)
- [NUSDownloader](/assets/files/NUSDownloader.zip)
- Une sauvegarde du NAND de votre console, avec le pied de page de NO$GBA
  - twlnf crée ce pied de page automatiquement quand une sauvegarde est faite
  - Vous devriez déjà avoir cette sauvegarde (voir Installer Unlaunch)
- [Scripts d'aide à l'installation de HiyaCFW](/assets/files/hiyacfw_helper.zip)

## Préparation
1. Insérez votre carte SD dans votre PC
2. Copiez  *le contenu* de l'archive `.zip` de NUSDownloader dans un dossier de votre PC
3. Copiez  *le contenu* de l'archive `.zip` de HiyaCFW dans un dossier de votre PC
4. Copiez  *le contenu* de l'archive `.zip` de l'aide à l'installation de HiyaCFW dans le dossier `for PC` du dossier de iyaCFW (étape 3)
5. Copiez  *le contenu* de l'archive `.zip` de ugopwn à la racine de votre carte SD
5. Copiez  *le contenu* de l'archive `.7z` de twlnf à la racine de votre carte SD puis renommez `twlnf.nds` en `boot.nds`
6. Copiez `console_id.txt` à la racine de votre carte SD (depuis une éventuelle autre carte SD utilisée pour Unlaunch)
  - Bien sûr ceci ne s'applique que si vous avez utilisé deux cartes différentes
7. Copiez `nand.bin` et `nand.bin.sha` à la racine de votre carte SD (depuis une éventuelle autre carte SD utilisée pour Unlaunch)
8. Ouvrez NUSDownloader sur votre PC
  - Ceci peut être fait grâce à [Mono](http://www.mono-project.com/) sur les systèmes Mac/Linux/*nix
9. Cochez "Create Decrypted Contents (*.app)", et décochez "Keep Enc. Contents"
10. Sélectionnez **Database > System (DSi) > System Menu (Launcher) > [Votre Region] > v512 > Start NUS Download!**
11. Quittez NUS Downloader
12. Allez dans **titles > 00030017484e41XX > 512** à l'intérieur de votre dossier NUS Downloader
13. Copiez `00000002.app` depuis le dossier `512` vers le dossier `for PC` de HiyaCFW
14. Copiez votre sauvagarde valide du NAND (`nand.bin`) dans le dossier `for PC` de HiyaCFW

## Instructions
1. Insérez votre carte SD dans votre console
2. Allumez votre DSi
3. Ouvrez Flipnote Studio
  - Assurez-vous que l'option *Calendrier au démarrage* est désactivée dans les options de Flipnote Studio
  - Si vous avez un autre exploit DSiWare installé alors ouvrez celui-ci et passez à l'étape 16
4. Sélectionnez **Voir une Flipnote > Carte SD > Choisir un dossier > User > ugopwn**
5. Cliquez sur la flipnote avec la moitié basse en rouge
6. Choisissez "Modifier"
7. Cliquez sur l'icone de grenouille dans le coin inférieur gauche
8. Cliquez sur l'icone de péliculle
9. Sélectionnez **Copier > Retour > Quitter**
10. Cliqez sur la seconde flipnote.
11. Cliquez sur l'icone de grenouille dans le coin inférieur gauche
12. Cliquez sur l'icone de péliculle
13. Cliquez sur l'icone de flèche vers la droite deux fois
  - Vous verrez une nouvelle page se créer
14. Cliquez sur le bouton Coller éxactement 122 fois.
15. Sélectionnez "Effacer" puis "Coller"
  - Ceci devrait lancer twlnf
16. Pressez **X** pour monter directement le NAND du système
17. Pressez **START** pour ouvrir le menu de twlnf
18. Pressez **R** pour effectuer une copie du NAND sur votre carte SD
  - Ceci peut prendre quelques minutes
  - Branchez votre système pendant cette étape afin d'éviter un quelconque problème d'alimentation
  - Quand `walk returned 0` apparaît, le processus est terminé
19. Une fois fini, pressez **Select** pour quitter twlnf
20. Pressez **A** pour confirmer
  - Votre console s'éteindra
21. Insérez votre carte SD dans votre PC
22. Déplacez tous les fichiers du dossier `dump` à la racine de votre carte SD
  - Ceci prépare le "SD NAND",  utilisé pour le démarrage de HiyaCFW
23. Allez dans le dossier `for PC` de HiyaCFW sur votre PC
24. Lancez `hiyacfw_helper.py` pour préparer les modifications
  - Ce script nécessite [WINE](https://www.winehq.org/){:target="_blank"} sur les systèmes Mac/Linux/*nix
25. Ouvrez le nouveau dossier `Modified Files`
26. Copiez `bootloader.nds` à la racine de votre carte SD
27. Copiez 00000002.app dans le dossier **title > 00030017 > 484e41XX > content** de votre carte SD
28. Copiez *le contenu* du dossier`for 2GB (or lower) SD card (SDNAND)` de HiyaCFW à la racine de votre carte SD
29. Ejectez votre carte SD et insérez-la dans votre console
30. Allumez votre DSi
  -L'écran de démarrage de HiyaCFW devrait aparaître

Votre système devrait maintenant démarrer depuis la carte SD au lieu du NAND.

[Fin de l'installation](/guide/fin-de-l'installation){: .btn .btn--light-outline}
{: style="text-align: center;"}