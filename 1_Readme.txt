#
# Neo4j Graph Database Containers mit Graphileon UI 
#


#
# Create a neo4j Container to store the Application Data of Graphileon
#

docker run \
    -d \
    --publish=7474:7474 \
    --publish=7687:7687 \
    --volume=$HOME/neo4j/data/graphileonApplication:/data \
    --name=graphileonApplication  \
    neo4j



#
# Create a neo4j Container to store the Business Data to work with
#

docker run \
    -d \
    --publish=7475:7474 \
    --publish=7688:7687 \
    --volume=$HOME/neo4j/data/graphileonDatastore:/data \
    --name=graphileonDatastore  \
    neo4j



#
# Note for first time use
#

By default Neo4j requires authentication. 
You have to login with neo4j/neo4j at the 
first connection and set a new password.



#
# To access the data via Browser
#

Zugriff auf das GUI des neo4j Containers graphileonApplication im Webbrowser mit 
    http://localhost:7474

Zugriff auf das GUI des neo4j Containers graphileonDatastore im Webbrowser mit
    http://localhost:7475

Zugriff auf Graphileon App im Webbrowser mit
    http://localhost:3001

Graphileon User Credentials (in this VM)
    pkmlp / pkmlp



Notes:

   Datastores are located in Folder neo4j/data of the user
   (to keep them persistent if a container will be deleted). 

        > /home/pkmlp/neo4j/data/graphileonApplication  --> Datastore for Graphileon App
        > /home/pkmlp/neo4j/data/graphileonDatastore    --> Datastore for Business Data 


   Delete persistent Neo4j Datastores: 
   
        > sudo rm -r /home/pkmlp/neo4j/data/graphileonApplication 
        > sudo rm -r /home/pkmlp/neo4j/data/graphileonDatastore       
        
            !!!!!!!!!! USE CAREFULLY !!!!!!!!!!


   To clean up:

        > /home/pkmlp/myTools/dockerCleanup

