# TP1 - Installation Linux sur une VM - V0.2

## Groupe 

-Pouly Steeve/Dias Alexandre

## But 

Cette manipulation a pour but d'installer une distribution linux [Sparky Linux](https://sparkylinux.org/) dans une machine virtuelle VMware Workstation Player, à l’aide d’une image disque (ISO).

## Materiels à disposition 

- VMware Workstation Player - V17
- Image disque (ISO) : sparkylinux-6.4-x86_64-minimalcli.iso

## Utilisation de VMware et de l'image ISO linux 

A. Lancez VMware Workstation Player (logiciel)  

B. Sélectionnez **Create a New Virtual Machine** 

C. Placez le fichier `.iso` dans une repertoire connu : 

`C:SPY`

D. Indiquez le chemin d’accès de l’image iso comme indiqué sous l’image ci-dessous :

![install image disk](/Images/Install_ISO.jpg) 

E. Choisir un nom d'OS : `Linux - Debian 11.x` 

![OS name choice](/Images/OS_Choice.jpg) 

F. Nommez la machine virtuelle : `SparkyLinux-SPY-AOD` 

G. Creez un disque virtuel -> capcité : **20GB** 

> remarque$$^1$$ : cocher **store virtual disk a single file**

![Virtual disk](/Images/VirtualDisk.jpg) 

> remarque$$^2$$ : ci-dessous, la configuration de la VM 

![Virtual disk](/Images/VM_Config.jpg) 

H. Lancez la machine virtuelle : **Play virtual machine** 

## Lancement de l'image ISO (Linux - Live CD) 

G. Lancement du live CD : 

![Lancement_du_live_CD](/Images/Lancement_du_live_CD.png) 

Shell Linux : 

![Shell_Linux](/Images/Shell_Linux.png) 

> **ATTENTION** : par défaut, le clavier est configuré est **Clavier Americain**

Q1. disposition du clavier américain ?

> QWERTY

Q2. disposition du clavier suisse-romand ?

> QWERTZ

Q3. disposition du le clavier français ? 

> AZERTY


H. Déplacez-vous à la **racine du système** en utilisant la commande suivante : `cd` 

> cd /

I. Affichez le contenu de la racine avec la commande : `ls –l`	

![Contenu_racine](/Images/Contenu_racine.png) 

Q5. Que signifie l'option `-l` avec la commande `ls` 

> c'est le format long de la commande ls, elle affiche les informations pour chaque fichier ou répertoire.

Q6. Décrypter la ligne où se trouve le répertoire **home**    

![Description_repertoire_ligne_home](/Images/Description_repertoire_ligne_home.png)

> d = indicateur de type de fichier la on se trouve dans le répertoire
> rwx = privilège que peux avoir l'utilisateur sur ce répertoire, ici on peut lire(r) écrire(w) executer(x)
> r-x = privilège que le groupe peut avoir sur ce répertoire, ici on peut lire(r) impossible d'écrire(-) executer(x)
> r-x = privilège qu'un utilisateur partagé peut avoir su ce répertoire, ici on peut lire(r) impossible d'écrire(-) executer(x)
> 1 = Le nbr d'accès
> root = racine utilisateur
> root = racine groupe
> 60 = espace mémoire utilisée 60 Mo
> Sep 18 = date du dernier acces ou modif de ce répertoire, ici c'est le 18 Septembre
> 14:04 = heure selon la date du dernier acces ou modif de ce répertoire, ici c'est à 14H04
> home = nom du répertoire

J. Créez un répertoire de travail nommé « EMSY_VosInitiales» dans quel dossier racine allez-vous le placer (justifiez votre réponse) et quelle commande allez-vous utiliser. 

> Dans le dossier home/live car on peut facilement y accéder et on arrive dessus lors du lancement de la machine virtuel.
> On utilise la commande "mkdir EMSY_SPY-AOD"

Q7. Si vous créez un répertoire de travail (pour éditer/sauvegarder des fichiers), dans quelle **répertoire racine** vous vous placez ? 

> On le mettrait dans un répertoire qui n'est pas sensible à des erreurs de commande ou des suppressions telle le répertoire "home"


K. Dans ce répertoire, créez un fichier texte que vous nommerez `TESTSLO_XXX_XXX` et éditez celui en écrivant un texte, exemple : "TP linux by XXX et XXX".
	Utiliser la commande `vi`

> vi TESTSLO_SPY_AOD.txt 

Q9. dans le répertoire `/home`, pouvez-vous éditez un fichier uniquement avec la commande `vi` 

> il faut ajouter le format du fichier ".txt" à la suite du nom.

Q10. Si vous éteignez la machine virtuelle et que vous la rallumez, est-ce que le répertoire créé ci-dessus existe toujours (justifiez votre réponse) ? 

> Non, car la machine virtuel est réinitialisé à son arret.

L. Tapez la commande `ls -l /dev/sda` 

![Commande_ls-l_dev_sda](/Images/Commande_ls-l_dev_sda.png) 

Q11. Que signifie **sda** ? 

> C'est la désignation actuelle pour désigner les disque dur, lors de l'installation linux donne le nom de sda au 1er disque dur.

Q12. Décrypter la réponse après avoir taper la commande `ls -l /dev/sda` -> voir résultat point 13.

> brw-rw----1 root disk 8,0 Sep 24 15:56 dev/sda
> b = indicateur de type de fichier la on se trouve dans le fichier bloc
> rw- = privilège que peux avoir l'utilisateur sur ce répertoire, ici on peut lire(r) écrire(w) impossible d'executer(-)
> rw- = privilège que le groupe peut avoir sur ce répertoire, ici on peut lire(r) écrire(w) impossible d'executer(-)
> --- = privilège qu'un utilisateur partagé peut avoir su ce répertoire, ici il est impossible de lire(-) impossible d'écrire(-) impossible executer(-)
> 1 = Le nbr d'accès.
> root = racine utilisateur.
> disk = block SCSI.
> 8 = numéro majeur, il indique le pilote utilisé gérer le matériel.
> 0 = numéro mineur, il est donné par le pilote pour distingué le matériel qu'il contrôle.

## Tips 

> $$Tips^1$$ : sortir de la VM -> appuyer simultanément sur `Ctrl` et `Alt` 

> $$Tips^2$$ : arrêter la VM proprement -> commande : `shutdown`

> $$Tips^3$$ : arrêter la VM pour cause de plantage -> commande : `halt` ou `poweroff`

> $$Tips^4$$ : [commande vi avec ses options](https://www.linuxtricks.fr/wiki/guide-de-sur-vi-utilisation-de-vi)

> $$Tips^5$$ : [éditer un fichier type markdown (.md)](https://ashki23.github.io/markdown-latex.html)

