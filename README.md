## Install-Crack-Confluence
- How to install cracked Confluence tested on versions 7.19.7 and 8.1.3

All thanks to these developers!
---
  - [sinanejadebrahim](https://github.com/sinanejadebrahim)
  - [haxqer](https://github.com/haxqer)
  - [Praying](https://github.com/Praying)


## These instructions are based on Ubuntu OS.

## Step 1, install and start postgresql with these commands.
```bash
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib -y
sudo update-rc.d postgresql enable
sudo service postgresql start
```

## Step 2, make a database
```bash
sudo -u postgres psql
postgres=# CREATE USER confluencedbadmin WITH PASSWORD 'password';
postgres=# CREATE DATABASE confluencedb WITH ENCODING 'UNICODE' LC_COLLATE 'C' LC_CTYPE 'C' TEMPLATE template0;
postgres=# GRANT ALL PRIVILEGES ON DATABASE confluencedb TO confluencedbadmin;
\q
```

## Step 3, download confluence from this link
```bash
wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-8.1.3-x64.bin
chmod a+x atlassian-confluence-8.1.3-x64.bin
sudo ./atlassian-confluence-8.1.3-x64.bin
```

## Step 4, just proceed with the installation, after the installation is complete do not start the confluence yet!
```
Installation of Confluence 8.1.3 is complete
Start Confluence 8.1.3 now?
Yes [y, Enter], No [n]
n
```

## Step 5, create a directory in the root folder and download the atlassian-agent
```bash
cd /
mkdir /var/agent
cd /var/agent
wget https://github.com/haxqer/confluence/releases/download/v1.3.3/atlassian-agent.jar
```

## Step 6, edit the environment and add this inside the 'setenv.sh'
```bash
cd / 
cd /opt/atlassian/confluence/bin
sudo vim setenv.sh
i
CATALINA_OPTS="-javaagent:/var/agent/atlassian-agent.jar ${CATALINA_OPTS}"
esc
:
wq
```

## Step 7, start the confluence
```bash
cd / 
sudo /opt/atlassian/jira/bin/start-confluence.sh
```

Now you can go to your browser and type your ip and assigned port to confluence
- Ex. 127.0.0.1:8090

## Step 8, crack confluence
- Once you started confluence it will ask you about the license key, to start cracking confluence enter this command
```bash
java -jar /var/agent/atlassian-agent.jar -p conf -m Hello@world.com -n Hello@world.com -o your-org -s you-server-id-xxxx
```

- This will generate a license key copy it and paste it inside the license key text box.
- Next, connect confluence to your created database. 
- Then proceed, it should work by now.
