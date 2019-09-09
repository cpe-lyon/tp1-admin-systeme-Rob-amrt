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
Cela est dû au fait que le programme sudo est différent du shell. La commande `cd` étant propre au shell, celle-ci ne peut être utilisée à l'intérieur du sudo.

#### Question 7 : A partir de votre dossier personnel, créez l’arborescence suivante :










