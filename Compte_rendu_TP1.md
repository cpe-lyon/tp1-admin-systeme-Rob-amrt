# TP 1 - Installation d’Ubuntu Server et prise en main du shell

### Exercice 2 Prise en main de l’interpréteur de commandes 

### Manuel

#### Question 1 : A l’aide du manuel, identifiez le rôle de la commande which
     
Grace à la commande :
`man which`    
On peut voir une description de ce à quoi sert la commande which.      
En utilisant la commande par exemple : 
`code which ls`    
Cela nous retourne :
`/usr/bin/ls`
La commande which sert donc à montrer le chemin où se situent les fichiers exécutés lors de l'execution d'une commande. 

#### Question 2 : Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option?
Pour trouver le mot 'Option', il faut à l'intérieur du fichier which taper : `/option`

#### Question 3 : Comment quitte-t-on le manuel? 
Il suffit d'appuyer sur la touche `Q`

#### Question 4 : Chaque section du manuel a une première page, qui présente le contenu de la section. Aﬀicher la première page de la section 6; de quoi parle cette section?
Pour parvenir à la première page de la section 6 du manuel, il faut utiliser la commande : `man 6 intro`
Nous pouvons voir que la section 6 est à propos des jeux et des différents programmes de divertissement disponible sur le système.

### Navigation dans l’arborescence des fichiers

#### Question 1 : allez dans le dossier /var/log 
Dans la console : `cd /var/log`

#### Question 2 : Remontez dans le dossier parent (/var) en utilisant un chemin relatif 
Dans la console : `cd ..`

#### Question 3 : Retournez dans le dossier personnel 
Dans la console : `cd`

#### Question 4 : Revenez au dossier précédent (/var) 
Dans la console : `cd -`

#### Question 5 : Essayez d’accéder au dossier /root; que se passe-t-il? 
Dans la console : `cd /root`
Cela nous retourne '-bash: /root: Permission denied'

#### Question 6 : Essayez la commande sudo cd /root; que se passe-t-il? Expliquez
On nous demande le mot de passe du root, puis que la commande `cd` est inconnu.
Cela est dû au fait que le programme sudo est différent du bash. La commande `cd` étant propre au shell, celle-ci ne peut être utilisée à l'intérieur du sudo.

#### Question 7 : A partir de votre dossier personnel, créez l’arborescence suivante :

Utilisez la commande `mkdir` pour créer des dossiers et la commande `touch` pour créer des fichiers
`mkdir dossier1 && touch dossier1/fichier1 && mkdir dossier2 && mkdir dossier2/dossier2.1 && mkdir dossier2/dossier2.2 && touch dossier2/dossier2.2/fichier2 && touch dossier2/dossier2.2/fichier3`

#### Question 8 : Revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis
Dossier1 ; que se passe-t-il ?
Fichier1 se supprime bien, cependant Dossier1 ne peut être supprimé car il s'agit d'un dossier. 

#### Question 9 : Quelle commande permet de supprimer un dossier ?
Pour supprimer un dossier, il faut utiliser la commande `rmdir`

#### Question 10 : Que se passe-t-il quand on applique cette commande à Dossier2 ?
On ne peut supprimer Dossier2, car le dossier n'est pas vide.

#### Question 11 : Comment supprimer en une seule commande Dossier2 et son contenu ?
En utilisant la commande `rm -d -r` cela efface le dossier ainsi que tout ce qu'il contient en même temps grace à l'attribut `-r`

### Commandes importantes

#### Question 1 : Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?
Pour afficher l'heure, il faut utiliser la commande `date`
La commande `time` permet d'afficher le temps que met une commande pour s'executer `time [commande]`

#### Question 2 : Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire
sur les fichiers commençant par un point ?
Les fichiers commençant par un point sont des fichiers cachés.

#### Question 3 : Où se situe le programme ls ?
Grace à la commande `which ls` on sais que la commande ls se situe ici : `/usr/bin/ls`

#### Question 4 : Que fait la commande ll ? (indice : la commande alias peut vous aider)
La commande `ll` est un alias permettant d'utiliser la commande à option `ls -l`

#### Question 5 : Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?
La commande `ls /bin`

#### Question 6 : Que fait la commande ls .. ?
Elle liste l'ensemble des fichiers et dossiers contenu dans le repertoir parent du dossier dans lequel nous nous trouvons. C'est à dire de l'echelon supérieur de l'arborescence.

#### Question 7 : Quelle commande donne le chemin complet du dossier courant ?
La commande `pwd`

#### Question 8 : Que fait la commande echo 'yo' > plop exécutée 2 fois ?
L'utilisation d'un seul symbole ">" permet de créer un fichier et y inscrire la chaine de caractère entre '' qui ici 'yo' inscrit dans le dossier plop. L'executé 2 fois ne change rien puisque 'yo' à déja été écrit dans le fichier.

#### Question 9 : Que fait la commande echo 'yo' >> plop exécutée 2 fois ?
L'utilisation de deux symboles ">>" permet de créer un fichier et y inscrir la chaine de caractère entre ''. Cependant ici les deux `>>` force l'inscription 'yo' à l'intérieur du fichier, même si celui-ci est déja présent.

#### Question 10 : A quoi sert la commande file ? Essayez la sur des fichiers de types différents.
La commande `file` permet de donner le type de fichier. Par exemple `file Dossier1` va nous retourner que Dossier1 est de type `Directory`

#### Question 11 : Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier
avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi :
qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?
Quand on modifie le contenu de toto, celui de titi change à l'identique et inversement. Si l'on supprime l'un des fichiers, l'autre continue d'exister en tant que fichier unique et garde le contenu.

#### Question 12 Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le
contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle
conséquence cela a-t-il sur tutu ?
Cela à le même effet qu'un lien classique, cependant, le fichier lié symboliquement ici Tutu est dépendant de son lien avec le fichier principal ici Titi. Tutu envoie les modifications de texte s'il y a lieu à Titi, sinon il ne fait que lire ce qui est contenu dans Titi, il ne stock rien. Donc si Titi disparais, Tutu ne peut plus rien afficher.

#### Question 13 : Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et
reprendre le défilement à l’écran ?
Les raccourcis sont `Ctrl+Q` pour activer et `Ctrl+S` pour interrompre

#### Question 14 : Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les
lignes 10 à 20.
- 5 première ligne : `head -5 /var/log/syslog`
- 15 dernières lignes : ` tail -15 /var/log/syslog`

#### Question 15 : Que fait la commande dmesg | less ?
La commande dmesg ou display message, permet de voir l'historique des messages du noyaux. La commande less quant à elle, ne quitte pas la pagination, il est donc possible de revenir en arrière sans relancer la commande, naviguer dans le fichier ouvert à l'aide des flèches de direction du clavier, passer d'une page à l'autre en appuyant sur la barre Espace ou F, revenir sur la page précédente en appuyant sur B (back), aller au début du fichier G, aller à la fin du fichier Shift+G et quitter avec Q.
Une option qui peut être intéressante est -N. Elle sert à numéroter les lignes du fichier affiché à l'écran (le fichier lu n'est aucunement modifié).

## Question 16 : Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page
de manuel de ce fichier ?

Le fichier /etc/passwd contient la liste de tous les utilisateurs systèmes ainsi que divers données sur leur compte comme l'id, le chemin d'accès au dossier utilisateur, le shell utilisé (/bin/false pour interdire).
La commande pour accéder au manuel de ce fichier est man 5 passwd.

#### Question 17 : Affichez seulement la première colonne triée par ordre alphabétique inverse

#### Question 18 : Quelle commande nous donne le nombre d’utilisateurs ?
La commande `who -q`

#### Question 19 : Combien de pages de manuel comportent le mot-clé conversion dans leur description ?

#### Question 20 : A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine
La commande `find` permet de trouver un fichier selon un chemin d'accès.
Pour tout le système la commande sera : `find / -name 'passwd'`

#### Question 21 : Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier
~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null
Pour cela nous utiliserons la commande `find / -name 'passwd' > ~/list_passwd_files.txt 2>/dev/null`
Le 2> permet d'esclure les erreurs.

#### Question 22 : Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment

#### Question 23 : Utilisez la commande locate pour trouver le fichier history.log.
La commande `locate history.log` nous dit que le fichier se situe dans /`var/log/apt/history.log`

#### Question 24 : Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?
Le mannuel nous apprend que la commande `locate` utilise une ou plusieurs base de donnée, mis à jour par la commande `updatedb` qui permet de relié pour chaque fichier son chemin de location.
Cette base de donnée se met à jour tout les 24H, d'où l'impossibilité de trouver des fichiers fraichement créé. Pour cela, il faut mettre la base de donnée à jour avec `updatedb`






