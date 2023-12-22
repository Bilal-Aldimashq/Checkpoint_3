# **Partie 1 : Gestion des utilisateurs**

**Q.2.1.1:**
Création d'un utilisateur:

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q211_1.png?raw=true)

_________________

**Q.2.1.2:**

Comme préconisation je propose de mettre cet utilisateur dans le groupe root, ce qui permettra lors de cession distante de pouvoir gérer le serveur en root.  
Il devra également être autorisé à ce connecté à distance en le renseignant dans le fichier /etc/ssh/sshd_config.  

_________________
_________________

# **Partie 2 : Configuration de SSH:**

**Q.2.2.1:**
Désactiver l'accès root à distance:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q221_1.png?raw=true)

________________

**Q.2.2.2:**
Autoriser l'utilisateur créer à ce connecter à distance:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q222_2.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q222_3.png?raw=true)

________________

**Q.2.2.3:**

Mise en place de l'authetification par clé:  

- Génération de la clé depuis le client:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_1.png?raw=true)

- Envoie de la clé vers le serveur:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_2.png?raw=true)

- Configuration du fichier sshd_config afin d'autoriser la connection à distance sans mot de passe:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_3.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_4.png?raw=true)

- Après redémarrage du service ssh avec la commande: systemctl restart sshd, connection sans mot de passe:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_5.png?raw=true)
