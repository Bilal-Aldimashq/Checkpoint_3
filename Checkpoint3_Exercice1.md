# **Partie 1: Gestion des utilisateurs:**

**Q.1.1.1:**

- Dans le gestionnaire AD, clic droit sur l'utilisateur Kelly Rhameur et sélectionner _copy_. Nommer le nouvel utilisateur Lionel Lemarchand. 
- Dans _Propriétés_ de Kelly Rhameur, changer le nom du manager des collaborateurs dans l'onglet _Organization_. Pour chaque collaborateur, double clic sur le nom, aller dans l'onglet -Organization_, puis cliquer sur _change_ afin de rentrer le nom de Lionel Lemarchand.

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q111_1.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q111_2.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q111_3.png?raw=true)

___________________
**Q.1.1.2:**

- Clic droit sur _TSSR.LAN_, _NEW_, _Organization Unit_, et rentrer le nom de l'OU _DesactivedUsers_.
- Clic droit sur Kelly Rhameur, Cliquer _Disable Account_.
- Clic droit sur Kelly Rhameur, cliquer _Move_, sélectionner l'OU _DesactivedUsers_.  

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q112_1.png?raw=true)

______________________
**Q.1.1.3:**

- Dans l'OU _Direction des Ressources Humaines_, cliquer sur le groupe _GrpUsersDirectionDesRessourcesHumaines_. Cliquer sur l'onglet _Members_, sélectionner Kelly Rhameur puis _Remove_.

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q113_1.png?raw=true)

______________________

**Q.1.1.4:**
Dossier renommer et archiver dans un dossier créé nommé ARCHIVES, toujours dans le répertoire **DossierIndividuels(F:)**:

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q114_1.png?raw=true)

Gestion des droits du dossier archiver afin qu'il ne puisse plus être consulté par les Utilisateurs:

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q114_2.0.png?raw=true)

Création du nouveau Dossier Individuel et gestion des droits:

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q114_3.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q114_4.0.png?raw=true)


_____________________
_____________________

# **Partie 2: Restriction des utilisateurs:**

**Q.1.2.1:**
- Sur la fiche de propriétés de Gabriel Ghul, aller sur l'onglet _Account_. Cliquer sur _Logon Hours_ et sélectionner la plage horaire.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q211_2.png?raw=true)

_____________________

**Q.1.2.2:**
- Toujours dans l'onglet _Account_, cliquer sur _Log On To..._.
- Cocher _The following computer_.
- Rentrer le nom de l'ordinateur, puis cliquer _Add_. Validant en cliquant _OK_.  
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q122_1.png?raw=true)

____________________

**Q.1.2.3:**
- Mettre les Utilisateurs dans leurs groupes respectifs. Les utilisateur dans l'OU ADV, vont dans le groupe ADV. Le groupe ADV étant Dans le groupe GrpUsersDirectionCommercial, cela facilitera la mise en place de la politique de mot de passe. On ajoute ensuite les managers dans leur groupe, pour l'OU Direction commercial c'est Pierre David que l'on rajoute à GrpUsersDirectionCommercial. Ainsi sur tout les OU de l'OU LabUsers.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_1.0.png?raw=true)
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_2.png?raw=true)

- Aller dans L'_Active Directory Administrative Center_, cliquer sur _TSSR(Local)_, _System_, _Password Setting Container_.
- Dans la colonne de droite cliquer _New_, _Password Setting_. et remplir le tableaux.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_3.png?raw=true)
- Ajouter les 11 groupes des OU Direction.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_4.png?raw=true)
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_5.png?raw=true)
- Valider avec _OK_, la règle apparaît dans le tableaux avec son nom, priorité, type et description.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q123_6.png?raw=true)
____________________
____________________

# **Partie 3: Lecteurs réseaux:**

**Q.1.3.1:**
- Clique droit sur le lecteur, cliquer _Properties_.
- Cliquer _Advanced Sharing_, cocher _Share this folder_ puis _OK_.
- Aller dans _Group Policy Management_.
- Clic droit _Group Policy Object_, _New_, nommer la GPO et validé avec _OK_.
- Clic droit sur la GPO _Drive-Mount_, _Edit_.
- Cliquer sur _User Configuration_, _Preferences_, _Windows Settings_, _Drive Maps_.
- Clic droit dns fenêtre de droite, _New_, _mapped drive_,
- Remplir le tableaux.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q131_1.0.png?raw=true)
- Valider avec _Apply_ et _OK_.
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q131_1.png?raw=true)

- Dans -Group Policy Management_, clic droit sur l'OU _LabUsers_, _Link a existing GPO_, cliquer sur la GPO _Drive-Mount_ puis _OK_.
- Sur la GPO _Drive-Mount_, cliquer sur l'onglet _Details_, sélectionner _Computer configuration settings disabled_ dans _GPO Status.

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q131_2.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q131_3.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q132_4.png?raw=true)
