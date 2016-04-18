WARNING: because MongoDB uses memory mapped files it is not possible to use it through vboxsf to your host vbox bug (https://www.virtualbox.org/ticket/819).

For OSX: tell docker to create a data volume in the container rather than the host, as follows:
docker run --name local-mongo -v mongo-data:/data/db -p 27017:27017 -d mongo

"-v mongo-data:/data/db": here we tell docker to create a new data volume called mongo-data and mount it as /data/db which is the default location mongo wants to write data to.