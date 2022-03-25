# Setup Mysql with docker and IntelliJ

## 1 Install docker

Clone the repository than 

For windows

Download docker from the [official web site](https://www.docker.com/get-started/) and install .

For Linux

Use your package manager and install docker and docker.io .


## 2 Create the container

Create a folder name **scripts-sql** .

Insert all your creation script in this folder .

Once done you can open a terminal in the folder where the **MysqlDocker** file is and run this command (*On linux run it as su*) : 

    docker build -t name_of_choice -f ./MysqlDocker .

## 3 Start the container

It's time to start your container now ! 

Run the next command (*On linux run it as su*):

    docker run --name name_of_choice -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password_of_choice -d name_of_choice

Well done your container run for the first time !

## 4 Intellij

Now head on Intellij and go in the settings and search for docker.

![Intellij setting](/images/1.png)

Once you find it click on it than the little plus, if all the setup went well you shoud see a message *Connection successful* !

## 5 Usage

Now you can see a little a new services .

![Servicies](/images/2.png)

You can start your container that is in the container section or manage your image and network from there now !

## 6 Connection

You can connect from anywhere just by going for the localhost (127.0.0.1) and the default port of MySQL 3306 .
## End

I hope this tutorial helped you !