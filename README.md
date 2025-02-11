# NetCat en Go (TCP-Chat)

## Description

Ce projet implémente une version simplifiée de la commande `NetCat` en utilisant Go. Il permet la création d'un chat en groupe basé sur une architecture serveur-client utilisant TCP. Le serveur peut gérer plusieurs clients simultanément et diffuser des messages entre eux.

## Fonctionnalités

- **Connexion TCP** entre un serveur et plusieurs clients (1 à 10 connexions).
- Chaque client doit fournir un **nom** pour participer au chat.
- Les clients peuvent échanger des **messages** en temps réel.
- Les messages sont horodatés et identifiés par le nom du client.
- Lorsqu'un client rejoint ou quitte, tous les autres clients sont **notifiés**.
- Support pour **plusieurs ports** (port par défaut : 8989).
- Les nouveaux clients voient **l'historique des messages** précédents.
- Gestion des **erreurs** côté serveur et client.
- **Go-routines** pour la gestion parallèle des connexions.
- Utilisation de **channels** ou **mutexes** pour la synchronisation des messages.

## Pré-requis

- Go 1.16 ou supérieur
- `netcat` pour tester les connexions des clients

## Packages Go Utilisés

- `io`
- `log`
- `os`
- `fmt`
- `net`
- `sync`
- `time`
- `bufio`
- `errors`
- `strings`
- `reflect`

## Installation

1. Clonez le projet :

    ```bash
    git clone https://github.com/votre-repository/net-cat-go
    cd net-cat-go
    ```

2. Exécutez le serveur :

    ```bash
    go run .
    ```

   Par défaut, le serveur écoutera sur le port `8989`. Pour utiliser un autre port, exécutez la commande suivante :

    ```bash
    go run . 2525
    ```

## Utilisation

### Lancer le Serveur

1. Par défaut, le serveur écoute sur le port 8989 :

    ```bash
    $ go run .
    Listening on port :8989
    ```

2. Vous pouvez également spécifier un autre port :

    ```bash
    $ go run . 2525
    Listening on port :2525
    ```

### Connexion des Clients

Pour connecter un client au serveur via NetCat (`nc`), ouvrez un nouveau terminal et tapez :

```bash
$ nc localhost 8989


