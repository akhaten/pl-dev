# Comment installer un environnement de travail pour la programmation linéaire dans un container docker ?

---

## Dependances :

Installer `docker` via votre gestionnaire de paquet.

Cloner ce repository avec la commande `git clone`

---

## Contenu du dossier :
- un fichier `Dockerfile` contenant la configuration minimale d'un container pouvant executer les commandes `scip` et `zimpl`.
- un dossier `workspace` où vous pouvez placer les tps d'algorithmique avancée. C'est votre espace de travail. Il est partagé avec le container. 
- un `.deb` correspondant à l'installateur `scip` et `zimpl` téléchargé au lien suivant : https://www.scipopt.org/index.php#download

---

## Utilisation :

---

### Créer le container :
```
user@user$ cd pl-dev
user@user$ sudo docker build . -t tp-algo
```
---

### Lancer le container avec un dossier paratagé :
```
user@user$ sudo docker run -it --mount src=$(pwd)/workspace,target=/home/workspace,type=bind tp-algo
```
Le terminal est celui de ubuntu 20.04. Utilisez lecomme bon vous semble.
La seule chose que vous ne pourrez pas faire c'est de créer ou de modifier 
des fichiers de votre workspace depuis le contener (à cause des permissions).

---

### Supprimer le container :

Quand vous n'avez plus besoin d'utiliser scip, zimpl...
vous pouvez supprimer le container
```
user@user$ sudo docker image rm -f tp-algo
user@user$ sudo docker image rm -f ubuntu:20.04
```
Vous pouvez vérifier que la désinstallation s'est bien passée avec :
```sh
user@user$ sudo docker image ls
```
