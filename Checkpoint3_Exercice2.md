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
Autoriser l'utilisateur créé à se connecter à distance:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q222_2.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q222_3.png?raw=true)

________________

**Q.2.2.3:**  

Mise en place de l'authentification par clé:  

- Génération de la clé depuis le client:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_1.png?raw=true)

- Envoie de la clé vers le serveur:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_2.png?raw=true)

- Configuration du fichier sshd_config afin d'autoriser la connection à distance sans mot de passe:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_3.png?raw=true)

![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_4.png?raw=true)

- Après redémarrage du service ssh avec la commande: _systemctl restart sshd_, connection sans mot de passe:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q223_5.png?raw=true)

___________________
___________________

# **Partie 3 : Analyse du stockage:**

**Q.2.3.1:**  
Les systèmes de fichiers montés sont du EXT4, EXT2 et du SWAP:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q231_1.png?raw=true)

________________

**Q.2.3.2:**  
Le RAID1 et du LVM sont utilisés:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q232_1.png?raw=true)

_______________

**Q.2.3.3:**  
Réparer le RAID1:  
On constate que le RAID1 est en mode dégradé dû à l'absence d'un 2ème volume de stockage:
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q233_1.png?raw=true)

- Un disque de 8Go est ajouter dans la machine.
- Avec la commande _lsblk_, on constate que le nouveau disque est présent sous le nom sdb.
- Partitionner le nouveau disque en tapant:
  ```bash
  fdisk /dev/sdb
  ```
- Choisr l'option _n_ pour un nouveau partitionement, validé les options par défaut pour partition primaire et la taille.
- Choisir l'option _t_ pour sélectionner le type de partition puis choisir l'option FD qui correspond au partionement d'un raid.
- Afin d'ajouter le nouveau disque au RAID éxistant faire:
  ```bash
  mdadm --manage /dev/md0 --add /dev/sdb1
  ```
- Contrôler la bonne reconstruction du RAID1 avec la commande:
  ```bash
  mdadm --detail /dev/md0
  ```
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q233_2.png?raw=true) 
_________
**Q.2.3.4:**  
Ajouter un nouveau LVM pour les sauvegardes: 
- S'assurer qu'il y a suffisemment d'espace libre dans le volume group, avec la commande _vgs_.
- Créer le volume logique _Save_ de 2go dans le VG _cp3-vg_ avec la commande:
  ```bash
  lvcreate -n Save -L 2g cp3-vg
  ```
- Formater le nouveau volume logique:
  ```bash
  mkfs -t ext4 /dev/cp3-vg/Save
  ```
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q234_1.png?raw=true)

- Créer un dossier pour le montage, _storage_, dans le répertoire /var/lib
- Monter le volume avec la commande:
  ```bash
  mount /dev/cp3-vg/Save /var/lib/storage
  ```
![](https://github.com/Bilal-Aldimashq/Checkpoint_3/blob/main/Ressources/Q234_2.png?raw=true)
