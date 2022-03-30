# Setup Mysql with docker and IntelliJ

You want a fast :zap: and lightweight way to have a mysql server to dev a cool app ? 

You are on the perfect tutorial ! :whale:
## 1 Needed files

Clone this repository.

## 2 Docker installation

For windows

Download docker from the [official website](https://www.docker.com/get-started/) and install .

Docker does need either Hyper-v or wsl 2 to run.

I suggest you wsl and there is the link to the [official install guide for wsl 1](https://docs.microsoft.com/en-us/windows/wsl/install).And the link for the [update to wsl 2](https://docs.microsoft.com/en-us/windows/wsl/install-manual) starting at step 4.

You may say a lot of install but wsl is a great tool to have but i ll make a separate github repository to speak about it.
(In short you can have a full linux running natively in windows that is way faster than a virtual machine)

For Linux

Use your package manager and install docker and docker.io .


## 3 Create the container

In the **scripts-sql**folder insert all your creation if you have it already. If not no worry i have already create a hello world script for this tutorial and when you have your final script either create the database using DataGrip, ... . But the best practice for docker would be to delete the older image and rebuild you container with the script in the **scripts-sql** folder.

Once done you can open a terminal in the folder where the **dockerfile** file is and run this command (*On linux run it as su*) :clipboard: : 

    docker build -t name_of_choice .

Need more details ?

-t will set the name of your image

we aren't giving the name or path of the file, cause in our case when the file is named dockerfile. When you run a build task in a directory, docker will try to find a dockerfile in the repertory where you run the task.
## 4 Start the container

It's time to start your container now ! 

Run the next command (*On linux run it as su*) :clipboard: : 

    docker run --name name_of_choice -p 3306:3306 -e MYSQL_ROOT_PASSWORD=password_of_choice -d name_of_choice

    docker start name_of_choice

Well done, your container run for the first time ! :zap:

Need more details ?

-p is the mapping of the port where you open on your container.

-d means detached, so the container will continue to run even if you close your terminal

--name will be the name of your container. You use to start, stop or interact with this container.

-e is a variable. In this case, it's used to set up your password to acces the database.
## 5 Intellij

Now head to Intellij and go to the settings and search for docker.

![Intellij setting](/images/1.png)

Once you find it click on it than the little plus, if all the setup went well you shoud see a message *Connection successful* !

## 6 Usage

Now you can see a little new services.
You can start your container that is in the container section or manage your image and network from there now !

![Servicies](/images/2.png)

Or you can be a bit fancy and do it from the command line with :clipboard: :

    docker start name_of_choice

    docker stop name_of_choice

    docker restart name_of_choice

You can also see all your container and image using :clipboard: : 

    docker container ls

    docker image ls

## 7 Connection

You can connect from anywhere just by going to the localhost (127.0.0.1) and the default port of MySQL 3306 . :fire:

## End

I hope this tutorial helped you ! :shipit:

Wrote by [Steven Sermeus] :fire:

If you have a question, either use GitHub or send me a private message on discord (Steven-Sensei#3484) :fire:
