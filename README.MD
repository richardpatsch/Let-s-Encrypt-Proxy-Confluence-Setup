#SSL Proxy / Let's encrypt - Confluence Setup#
Simple setup to run confluence behind an SSL proxy with automatic certificate renewal.

##modify the following environment variables in the docker-compose file:##
* CONFLUENCE_PROXY_NAME (replace with your confluence domain)
* LETSENCRYPT_EMAIL (your email)
* LETSENCRYPT_HOST (your confluence domain)
* VIRTUAL_HOST (your confluence domain)
* POSTGRES_PASSWORD (new database password; although the port is not forwarded from docker, it is a good idea to change it)

##Volumes:## 
* '/volumes/backups/:/var/atlassian/confluence/backups' 
  (replace the /volumes/backups path with the path to your local backup folder)

##Possible issues:##
* It may be necessary to increase the timeout within the nginx config, because if confluence times out during the setup, confluence will not work.