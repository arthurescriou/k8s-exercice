### Exercice 4: Nombre de worker dynamique

On utilise cette commande, après avoir modifié la gestion des ports:

`docker-compose up -e TASKS=50 -d --scale planner=1 --scale workeradd=10 --scale workermult=10`

`-e` sert à modifier la variable d'environnement du nombre de tâches, `--scale` à indiquer le nombre d'instances à créer pour le conteneur qui suit.

### Exercice 5: On mélange tout

De même, mais en réajoutant un worker général sans contrainte sur le type d'opérations, par exemple:

```
worker:
        environment:
            - PORT=3002
        build:
            context: ./worker
            dockerfile: Dockerfile
        image: worker
        container_name: worker
        ports:
            - "3002:3002"
        extra_hosts: 
            - host.docker.internal:host-gateway```