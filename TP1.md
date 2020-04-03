## Nathan Mittelette - Eloi Bellet

# TP1

## Exercice 2. Prise en main de l’interpréteur de commandes

### Manuel
1. A l’aide du manuel, identifiez le rôle de la commande `which`

> La commande which sert à localiser la fichier source associé à une commande donnée en paramètre.

2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercherle termeoptiondans la page de manuel de `which` ?

> Il faut appuyer sur la touche `/` et taper le contenu de la recherche

3. Comment quitte-t-on le manuel ?

> On quitte le manuel en appuyant sur la touche `q`

4. Chaque `section` du manuel a une première page, qui présente le contenu de la section. Aﬀicher la première page de la section 6; de quoi parle cette section?

> Le titre de la section est MISCELLANEOUS COMMANDS

### Navigation dans l’arborescence des fichiers

1. Allez dans le dossier `/var/log`

> `cd /var/log`

2. Remontez dans le dossier parent `/var` en utilisant un chemin relatif

> `cd ..`

3. Retournez dans le dossier personnel

> `cd /`

4. Revenez au dossier précédent (`/var`) `sans utiliser de chemin`

> `cd -`

5. Essayez d’accéder au dossier `/root`. Que se passe-t-il ?

> Je n'ai pas les droits pour accéder au dossier root

6. Essayez la commande `sudo cd /root`. Que se passe-t-il ? Expliquez.

> Il me demande mon mot de passe pour vérifier que j'ai bien le droit d'accéder au dossier root. Une fois l'authentification faite je peux accéder au dossier root

7. à partir de votre dossier personnel, créez l’arborescence suivante :



> La création de l'arborescence est faîte grâce à la commande `mkdir` pour créer un répertoire, `touch`pour créer un fichier et `cd` pour naviguer à travers l'arborescence.

8. Revenez dans votre dossier personnel. à l’aide de la commande `rm`, essayez de supprimer `Fichier1`, puis `Dossier1`. Que se passe-t-il ?

>  - `rm Dossier1/Fichier1`
>  - Il ne veut pas supprimer le dossier car la commande n'est pas faîte pour supprimer un dossier mais un fichier

9. Quelle commande permet de supprimer un dossier?

> C'est la commandez `rmdir`

10. Que se passe-t-il quand on applique cette commande à `Dossier2` ?

> Il ne peut pas supprimer le dossier car il n'est pas vide

11. Comment supprimer en une seule commande `Dossier2` et son contenu?

> Il faut utiliser l'option `--ignore-fail-on-non-empty`

### Commandes importantes

1. Quelle commande permet d’aﬀicher l’heure ? A quoi sert la commande `time` ?

> C'est la commande `date` qui permet d'afficher l'heure ainsi que la date

2. Dans votre dossier personnel, tapez successivement les commandes `ls` puis `la`. Que peut-on en déduire sur les fichiers commençant par un point ?

> Ça permet de résumer les ressources systemes utiliser par chaque utilisateur

3. Où se situe le programme `ls` ?

> La commande `ls` se trouve dans le dossier `/bin` soit l'arboresence `/bin/ls`

4. Essayez la commande `ll`. Existe-t-il une entrée de manuel pour cette commande ? Utilisez les commandes `alias `ou `alias` pour en savoir plus sur la nature de cette commande.

> Il n'existe pas de d'entrée manuelle pour la commande `ll`, Après execution de la commande alias ll on s'aperçois que la commande ll est un alias qui effectue la commande `ls -alF`

5. Quelle commande permet d’aﬀicher les fichiers contenus dans le dossier `/bin` ?

> C'est la commande `ls /bin`

6. Que fait la commande `ls` ?

> Elle affiche le contenu du dossier parent

7. Quelle commande donne le chemin complet du dossier courant ?

> C'est la commande `pwd`

8. Que fait la commande `echo 'yo' > plop ` exécutée 2 fois ?

> Cette commande permet d'écrire dans le fichier plop le contenu suivant : `yo`

9. Que fait la commande `echo 'yo' >> plo` pexécutée 2 fois?

> Cette commande permet d'écrire dans le fichier plop le contenu suivant : `yoyo`

10. A quoi sert la commande `file` ? Essayez la sur des fichiers de types différents

> - La commande `file` permet de déterminer le type du fichier pointé
> - `file plop` permet de savoir que c'est un fichier de type ASCII

11. Créez un fichier `toto` qui contient la chaîne `Hello Toto !`. Créer ensuite un lien `titi` vers ce fichier avec la commande `ln toto titi`. Modifiez à présent le contenu de `toto` et aﬀichez le contenu de `titi` : Qu’observe-t-on ? Supprimez le fichier `toto`. Quelle conséquence cela a-t-il sur `titi`?

>- `echo 'Hello Toto !' > toto`
>- `ln toto titi`
>- `echo 'Hello' > toto`
>- `cat titi`
>- On remarque que le contenu de titi a changé
>- Une fois que toto est supprimé le contenu de titi reste inchangé

12. Créez à présent un lien symbolique `tutu` sur `titi` avec la commande `ln -s titi tutu`. Modifiez le contenu de `titi`; quelle conséquence pour `tutu` ? Et inversement? Supprimez le fichier `titi`; quelleconséquence cela a-t-il sur `tutu`?

>- `echo 'Hello titi !' > titi`
>- `ln -s titi tutu`
>- `echo 'Hello' > tutu`
>- `cat titi`
>- On remarque que le contenu de titi a changé
>- `echo 'Hello Test' > titi`
>- `cat tutu`
>- On remarque que le contenu de tutu a changé
>- `rm titi`
>- Une fois que titi est supprimé il n'est plus possible de lire le contenu de tutu

13. - `cat /var/log/syslog`
    - La commande qui permet d'interromptre le processus est `Ctrl + C`

14. - `head -n 5 /var/log/syslog`
    - `tail -n 15 /var/log/syslog`
    - `head /var/log/syslog -n 20 | tail -n 10`

15. La commande `dmseg | less` permet d'afficher les messages du noyau par partie et de l'afficher au fur et à mesure

16. La commande `cat /etc/passwd` permet d'afficher les attributs des différents comptes du système.

17. `cut -d: -f1 /etc/passwd | sort +1`

18. `wc -l /etc/passwd`

19. A COMPLETER !!

20. `sudo find / -name passwd`

21. `find / -name passwd 2> /dev/null > ~/list_passwd_files.txt`

22. `grep -rl "alias ll='ls -alF'" / 2> /dev/null`

23. `locate history.log`

24. Le fichier n'apparait pas car il n'a pas eu le temps d'être mis dans la base de donnée qu'utilise la commande locate pour faire la recherche des fichiers

### Travailler avec plusieurs shells

## Exercice 3. Découverte de l’éditeur de texte nano

1. `cp /var/log/syslog ~/log.txt && nano ~/log.txt`

2. `nano ~/log.txt`
    Puis ALT+R, écrire le mot à remplacer, le mot de remplacement, A pour remplacer toutes les occurences

3. `nano ~/log.txt`
    Commencer la selection du bloc avec ctrl+shift+6, puis fleche du bas pour selectionner 10 lignes, puis ctrl+k pour couper, ctrl+fleche du bas pour aller à la fin du fichier, et enfin, ctrl+u pour coller

4.  ctrl+u *2 (annulation du paste et du cut)

5.  ctrl+s, puis ctrl+x pour quitter

## Exercice 4. Personnalisation du shell

1) `cp ~/.bashrc ./bashrc_bak`

2) La ligne `force_color_prompt=yes` dans le fichier `~/.bashrc` permet d'afficher des couleurs dans le shell

3) `source .baschrc`

4) `\[\e[35\][\A] - \[\e[32\]\u@\h:\[\e[36m\]\w\[\033[00m\]`
