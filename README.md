# fleet_mgt
Fleet Management system
## Development setup
### Prerequisites
* [Git](https://git-scm.com/download/win)
* [Sourcetree](https://www.sourcetreeapp.com/)(Git GUI)
### Installation
* Create a Github account with your company email.<br />
* Install Git and Sourcetree. Follow the [instruction](https://www.awordfromnet.com/how-to-connect-github-with-sourcetree/) to connect your Github account.
* Create a folder named 'project'. Clone the 'fleet_mgt' repository into the 'project' folder using Sourcetree.

## Frontend
### Built with
* Vue.js (Vue3, Vite)
### Prerequisites
* [Visual Studio Code](https://code.visualstudio.com/download) (IDE)
* [Node.js](https://nodejs.org/en)
### Installation
* Open the 'frontend' folder in Visual Studio Code.
* Enter the following commands to use the package manager npm to install packages.<br />
  `npm install`
* Enter the following commands to start the server. <br />`npm run serve`
* You can read the 'scripts' property in the package.json file to check commands for Vue.js.

## Database
### Prerequisites
* [VM](https://www.virtualbox.org/wiki/Downloads) (Oracle VM VirtualBox)
* [Ubuntu Server](https://ubuntu.com/download/server) (Ubuntu server image for VM)
* [PgAdmin](https://www.pgadmin.org/download/) (PostgreSql GUI)
* [PostgreSql](https://www.postgresql.org/download/linux/ubuntu/) (Install PostgreSql via command on the ubuntu server)
### Installation
* Open Oracle VM VirtualBox. Click 'new' to create virtual a ubuntu server with the ubuntu server image (.ISO).
* Install PostgreSql on ubuntu. Follow the [instruction](https://protocoderspoint.com/config-postgresql-remote-connection-access-using-pgadmin/)
  to set a password for PostgreSql and enable PostgreSql remote connection.
* Enter the following commands to install the net-tools package.<br />
  `sudo apt-get update`<br />
  `sudo apt-get -y install net-tools`<br />
  `sudo apt-get upgrade`
* Enter `ifconfig` to check ubuntu's IP address on the ubuntu server.
* Stop the ubuntu server. Click 'Setting' -> 'Network', change 'Attached to' to 'Host-only Adapter'.
* Open PgAdmin, right click server -> register -> create server -> enter 'postgres' in 'name'.
* Click 'Connection', enter your ubuntu IP address in 'Host name/address' and enter the PostgreSql password you set.
* Create a database named 'Rfleet' with PgAdmin.

## Backend
### Built With
* Spring Boot (Gradle)
### Prerequisites
* [Intellij](https://www.jetbrains.com/idea/download/#section=windows) (IDE)
* [Java 18](https://www.oracle.com/java/technologies/javase/jdk18-archive-downloads.html)
* [Gradle](https://gradle.org/install/)
### Installation
* Set a JAVA_HOME environment variable after installing java.
* Open the 'backend' folder in intellij.
* Click 'MainAppllication' on the top toolbar -> 'edit configuration'.
* Copy 'DATABASE_TYPE=pgsql;DB_HOST={ };DB_NAME=Rfleet;DB_PASSWORD={ };DB_USERNAME=postgres;DEBUG=true;USE_DEFAULT_DATA=true' to environment variables. DB_HOST is your ubuntu's IP,DB_PASSWORD is your PostgreSql password.
* Run the server and check whether the database's tables exist in PgAdmin.