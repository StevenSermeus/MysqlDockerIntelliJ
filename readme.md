# Setup Mysql with docker and IntelliJ

You want a fast :zap: and lightweight way to have a mysql server to dev a cool app ? 

You are on the perfect tutorial ! :whale:
## 1 Needed files

Clone the repository

## 2 Install docker

For windows

Download docker from the [official web site](https://www.docker.com/get-started/) and install .

For Linux

Use your package manager and install docker and docker.io .


## 3 Create the container

Create a folder name **scripts-sql** .

Insert all your creation script in this folder .

Once done you can open a terminal in the folder where the **dockerfile** file is and run this command (*On linux run it as su*) :clipboard: : 

    docker build -t name_of_choice -f ./dockerfile .

## 4 Start the container

It's time to start your container now ! 

Run the next command (*On linux run it as su*) :clipboard: : 

    docker run --name name_of_choice -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password_of_choice -d name_of_choice
    docker start name_of_choice
Well done your container run for the first time !

## 5 Intellij

Now head on Intellij and go in the settings and search for docker.

![Intellij setting](/images/1.png)

Once you find it click on it than the little plus, if all the setup went well you shoud see a message *Connection successful* !

## 6 Usage

Now you can see a little a new services .

![Servicies](/images/2.png)

You can start your container that is in the container section or manage your image and network from there now !

Or you can be a bit fancy and do it from the command line with

    docker start name_of_choice

    docker stop name_of_choice

    docker restart name_of_choice

You can also see all your container and image using 

    docker container ls

    docker image ls

## 7 Connection

You can connect from anywhere just by going for the localhost (127.0.0.1) and the default port of MySQL 3306 . :fire:

## End

I hope this tutorial helped you ! :shipit:
