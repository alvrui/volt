# volt

Exported docker file ready to imported as image with 
docker import <http://filename>

once ready check the image with
$ docker image ls
run it with
$ docker run -ti -p 8000:8000 voltvotes /bin/bash
--->
# su postgres
# <provide password>
$ cd /usr/local/helios-server
$ python manage.py runserver
  
the app is supposed to be accesible via browser on localhost:8000
