# airavata-file-manager

A simple SFTP Server implementation to integrate with Apache Airavata and any
OAuth authorization server

## Installation

1. Clone the repository

   ```
   git clone https://github.com/SciGaP/airavata-file-manager.git
   ```

2. Modify the filemgr.properties file accordingly. Make sure to specify a free
   port that is also open in the firewall.

3. Run `mvn package` to package up the code into a single jar file
   (`target/airavata-file-manager-X.Y-SNAPSHOT.jar`).

4. Use the file `scripts/init-script` as an init script for the service.
   Copy/rename the file into `/etc/init.d/` and modify the variables at the top
   of the script. Then run `service <name of init-script> start` to start the
   service.

### Testing the installation

To test, you'll need an OAuth access token. Using the airavata-django-portal,
you can get an access token by logging into /auth/login-desktop (for example,
for SEAGrid you would login at <https://seagrid.org/auth/login-desktop>). After
you login the `code` query parameter will contain the access token.

With the access token you should be able to use an SFTP client to login. I've
had success with the Cyberduck SFTP client. Set the hostname, port, your
username and use the access token for the password.
