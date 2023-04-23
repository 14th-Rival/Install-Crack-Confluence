# Install-Crack-Confluence
- How to install cracked Confluence tested on versions 7.19.7 and 8.1.3

All thanks to this developers!
---
  -@sinanejadebrahim

  @haxqer

  @Praying


# This instructions are based on Ubuntu OS.

First, install and start postgresql with these commands.
```
sudo apt-get update
sudo apt-get install postgresql postgresql-contrib -y
sudo update-rc.d postgresql enable
sudo service postgresql start
```

Second, make a database
```
sudo -u postgres psql
postgres=# CREATE USER jiradbadmin WITH PASSWORD 'password';
postgres=# CREATE DATABASE jiradb WITH ENCODING 'UNICODE' LC_COLLATE 'C' LC_CTYPE 'C' TEMPLATE template0;
postgres=# GRANT ALL PRIVILEGES ON DATABASE jiradb TO jiradbadmin;
\q
```

Third, download confluence from this link
```
wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-8.1.3-x64.bin
chmod a+x atlassian-confluence-8.1.3-x64.bin
sudo ./atlassian-confluence-8.1.3-x64.bin
```

Fourth, just proceed with the installation, after the installation is complete do not start the confluence yet!
```
Installation of Confluence 8.1.3 is complete
Start Confluence 8.1.3 now?
Yes [y, Enter], No [n]
n
```

Fifth, create a directory in the root folder
```
cd /
mkdir /var/agent
```

Sixth, download the atlassian-agent 
```
cd /var/agent
wget https://github.com/haxqer/confluence/releases/download/v1.3.3/atlassian-agent.jar
```

Seventh, edit the environment
```
cd / 
cd /opt/atlassian/confluence/bin
sudo vim setenv.sh
```

Eighth, place this line inside the 'setenv.sh'
  - CATALINA_OPTS="-javaagent:/var/agent/atlassian-agent.jar ${CATALINA_OPTS}"
```
i
CATALINA_OPTS="-javaagent:/var/agent/atlassian-agent.jar ${CATALINA_OPTS}"
esc
:
wq
```

Ninth, start the confluence
```
cd / 
sudo /opt/atlassian/jira/bin/start-jira.sh
```

Now you can go to your browser and type your ip and assigned port to confluence
- Ex. 127.0.0.1:8090

Tenth, crack confluence
- Once you started confluence it will ask you about the license key, to start cracking confluence enter this command

```
java -jar /var/agent/atlassian-agent.jar -p conf -m Hello@world.com -n Hello@world.com -o your-org -s you-server-id-xxxx
```

- This will generate a license key copy it and paste it inside the license key text box.
- Next, connect confluence to your created database. 
- Then proceed, it should work by now.
---
Hopefully this will help you!
