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
5 première ligne : `head -5 /var/log/syslog`







