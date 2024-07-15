# Docker bulk Down and Up

Run "down" and "up" on multiple docker-compose.yml found in specific directory automatically.

## Code

```bash
#!/bin/bash

# Change this to the directory where your docker compose files are located. The search
# for docker-compose.yml is recursive.
PROJECTDIR=/home


bring_down_all() {
    for dir in $(find $PROJECTDIR -type f -name 'docker-compose.yml' -exec dirn>
        echo "Bringing down Docker Compose in $dir"
        (cd $dir && docker compose down)
    done
}

bring_up_all() {
    for dir in $(find $PROJECTDIR -type f -name 'docker-compose.yml' -exec dirn>
        echo "Bringing up Docker Compose in $dir"
        (cd $dir && docker compose up -d)
    done
}

bring_down_all
bring_up_all
``` 
