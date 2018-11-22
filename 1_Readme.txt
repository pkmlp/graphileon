#
# neo4j Graph Database Containers mit Graphileon UI in VM
#

docker run \
    -d \
    --publish=7474:7474 \
    --publish=7687:7687 \
    --volume=$HOME/neo4j/data/graphileonApplication:/data \
    --name=graphileonApplication  \
    neo4j

docker run \
    -d \
    --publish=7475:7474 \
    --publish=7688:7687 \
    --volume=$HOME/neo4j/data/graphileonDatastore:/data \
    --name=graphileonDatastore  \
    neo4j

    By default Neo4j requires authentication. 
    You have to login with neo4j/neo4j at the 
    first connection and set a new password.



Zugriff auf das GUI des neo4j Containers graphileonApplication im Webbrowser mit 
    http://localhost:7474

Zugriff auf das GUI des neo4j Containers graphileonDatastore im Webbrowser mit
    http://localhost:7475

Zugriff auf Graphileon App im Webbrowser mit
    http://localhost:3001




Hinweise:

   Die Datenbanken werden im Home-Verzeichnis im Folder neo4j/data angelegt 
   und bleiben bestehen, auch wenn Container gelöscht werden. 

        > /home/pkmlp/neo4j/data/graphileonApplication  --> die Daten der Graphileon App
        > /home/pkmlp/neo4j/data/graphileonDatastore    --> die Business Daten (Service Komponenten und deren Abhängigkeiten)


   Um diese zu löschen: 
   
        > sudo rm -r /home/pkmlp/neo4j/data/graphileonApplication 
        > sudo rm -r /home/pkmlp/neo4j/data/graphileonDatastore       !!!!!!!!!! USE CAREFULLY !!!!!!!!!!


   Um die gestoppten Container, die Images und alle anderen Docker-Units wegzuräumen:

        > /home/pkmlp/myTools/dockerCleanup
