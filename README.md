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

Installation:
Install helios
Requirements locally. -> docker

docker pull ubuntu
docker run -ti ubuntu /bin/bash
apt update
apt upgrade
apt install sudo
useradd volt
passwd volt
adduser volt sudo
apt install postgresql git python-psycopg2 python-django python-setuptools python-pip python-httplib2 python-oauth2client python-celery python-bleach python-unicodecsv
PATH="/usr/lib/postgresql/10/bin:$PATH"
cd /usr/local/
mkdir pgsql
cd pgsql/
mkdit data
chown -R postgres /usr/local/pgsql/
sudo chown -R volt:volt /var/run/postgresql
PATH="/usr/lib/postgresql/10/bin:$PATH"

/usr/lib/postgresql/10/bin/initdb  -D /usr/local/pgsql/data
/usr/lib/postgresql/10/bin/pg_ctl -D /usr/local/pgsql/data -l logfile start
IF FATAL
sudo chown -R postgres:postgres /var/run/postgresql
sudo git clone --recursive git://github.com/benadida/helios-server.git 
sudo git clone http://github.com/openid/python-openid
cd python-openid
sudo python setup.py install
pip install validate_email
pip install South
settings.py helios dir: EDIT>>>
                            DATABASE_NAME = 'volt'             
                            DATABASE_USER = 'volt'             
                            DATABASE_PASSWORD = 'volt'         
                        DEFAULT_FROM_EMAIL = 'Alvaro is testing <alvaro.ruiz@volteuropa.org>'
                        # these three hosts should all be the same for dev
                        # e.g. http://localhost:8000
                        URL_HOST = "http://127.0.0.1"
                        SECURE_URL_HOST = "https://127.0.0.1"
                        SOCIALBUTTONS_URL_HOST = "http://127.0.0.1"
                        # FOOTER links
                        FOOTER_LINKS = [{'url':'http://usg.princeton.edu/elections', 'text':'blahblah edit this USG Elections Center'}
                        WELCOME_MESSAGE = "alea iacta est"

psql -U postgres
CREATE USER volt WITH PASSWORD 'volt';
CREATE DATABASE volt OWNER volt;
CREATE DATABASE helios OWNER volt;
\l
\q
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
./reset.sh
python manage.py runserver

COMMITED
docker run -ti -p 8000:8000 voltvotes /bin/bash
