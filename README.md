# AWS
creating vm by using aws 
1. make a aws account
2. search EC2
3. launch instance
4. name the instance
5. choose free tire
6. create private key
7. download the key , save it to desktop
8. select ssh and http
10.launch the instance 
11. go to see all instances there you will find the public ip
12. open the ip in another tab (it will not open because nothing is in there)
13. download install putty
14. go to session , enter the ip adress in the new host name 
15. go to ssh the go auth , expand auth
16. click credentials
17. browse private key and open the private key you downloaded
18. go to session and open it
19. your vm is now created
20. install 


  TO OPEN A WEB SERVER---<br/>
1.TYPE ON GOOGLE HOW TO INSTALL WEB SERVER IN YOUR OS WHICH YOU HAVE SELECTED.<br/>
2.NOW DOWNLOAD ANY WEB SERVER LIKE APACHE2ETC.<br/>
3.FROM THAT INSTALL APACHE2 IN YOUR VM<br/>
TYPE : >>sudo apt update<br/>
       >>sudo apt install apache2<br/>
<br/>
---PRESS ENTER AND WEB SERVER WILL START INSTALLING----<br/>
4.TO SEE THE WEB SERVER GO TO GOOGLE OPEN NEW TAB AND ENTER YOU IP ADDRESS . YOU WILL SEE THE APACHE2 WEB SERVER.<br/>
-----------TO SEE HI ON SERVER ---------------<br/>
1.ENTER THE FOLLOWING COMMAND<br/>
  >>cd{ENTER SPACE}/var/www/html/<br/>
  >>ls<br/>
  >>YOU WILL SEE<br/>
  >>index.html<br/>
  ------TO REMOVE SUDO-----------<br/>
  >>sudo su<br/>
  --------NOW SUDO IS REMOVED--------<br/>
<br/>
  -------REMOVE THE APACHE2 SERVER -----------<br/>
  >>rm index.html<br/>
  ------THEN ENTER--------<br/>
  >>vi index.html<br/>
  ------PRESS {i} -------<br/>
  ----------ENTER----------<br/>
  >><html>  hi   </html><br/>
  ------NOW PRESS THESE KEY-------<br/>
  >>ctrl+c<br/>
  <br/>
  -------REMOVE THE APACHE2 SERVER -----------<br/>
  >>rm index.html<br/>
  ------THEN ENTER--------<br/>
  >>vi index.html<br/>
  ------PRESS {i} -------<br/>
  ----------ENTER----------<br/>
  >><html>  hi   </html><br/>
  ------NOW PRESS THESE KEY-------<br/>
  >>ctrl+c<br/>
  >>shift+";"<br/>
  >>wq<br/>
  -------PRESS ENTER -------<br/>
  NOW GO TO GOOGLE AND ENTER THE IP ADDRESS YOU WILL SEE HII<br/>
  ---------------------------------------------------------------------------------------------------------------------<br/>
<br/>
<br/>
<br/>
<br/>


               1  rm index.html
    2  ls
    3  vi index.html
    4  history
root@ip-172-31-84-226:/var/www/html#





# CONTAINER
---
USING CONTAINER's IN VM , USNIG  DOCKER TO ADD NGINX SEVER IN IT AND TYPING HI IN WEB SERVER <br/>
 1. First I login in my AWS account . Thne I created an instance .<br/>
 2. In instance  I make some changes , where I edit in network setting , where I added SSH , HTTPS , HTTP, ALL TRAFFIC , ALL TCP , ALL UDP AND CREATED AN INSTANCE.<br/>
 3. Then I open puuty add the IP address from instance and add key pair file which I have downloaded when I creating instance.<br/>
 4. After that I click  on open , then my ubuntu terminal was opended , where I logined by writting ubuntu.<br/>
 5. After that I have to install docker in my OS .<br/>
 6. Then , I enter few command to  install the docker<br/>
 7. COMMANDS ARE:<br/>
>> 1. curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash<br/>
>> 2. newgrp docker  # this command will help us to use docker<br/>
>> 3.docker ps      # provides a list of the Docker containers on your machine<br/>
>> 4. docker --version # to check the version of docker which is installed<br/>
>>  5. docker pull nginx #TO use nginx server in container<br/>
>> 6. docker run --name docker-nginx -p 80:80 nginx  #In a web browser, enter your server’s IP address to reveal Nginx’s default landing page<br/>
>> 7. ctrl + c  #to stop the container from running<br/>
>> 8.  docker ps -a #The output reveals that the Docker container has exited<br/>
>> 9.  DETACHED MODE<br/>
>> 10. docker run --name docker-nginx -p 80:80 -d nginx #output is the container’s ID <br/>
>> 11. docker ps # provoide new information about container<br/>
>> 12. docker stop docker-nginx # to stop the container<br/>
>> 13. docker rm docker-nginx<br/>
>> Building a Web Page to Serve on Nginx<br/>
>>  14. mkdir -p ~/docker-nginx/html # Create a new directory for the website content within the home directory<br/>
>> 15. cd ~/docker-nginx/html # Create an HTML file to serve on the server<br/>
>> 16. ls<br/>
>> 17. cd html/<br/>
>> 18.ls # will show index.html file<br/>
>> 19.sudo vi index.html<br/>
>> 20.  press {"i"} # help to insert in the web server<br/>
>>  21. <html> hi </html> # write whatever you want to write I write only hi<br/>
>>  22. ctrl + c<br/>
>>  23. shift + ;<br/>
>> 24. wq   press {ENTER}<br/>
>>  25. docker run --name docker-nginx -p 80:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx # Linking the container to the VM<br/>
>>>>>>>>>> After running that command, enter the server’s IP address into the browser to view the  new landing page<br/>




# 3. USING MINIKUBE IN AWS

**First open aws search EC2 then Launch Instance and select 22.04 AMI then select t2.xlarge instance type then select keypair then configure storage to 30 GB then enable all traffic in network and Launch.**

**Now connect it with putty and login into it by writing ubuntu**

### Now put some commands

```
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
```
**it will install docker**




```
sudo usermod -aG docker $USER
```
```
newgrp docker
```

**it will Add your local user to docker group so that your local user run docker commands**






```
sudo snap install kubectl --classic
```
**it will intall kubectl tools**





```
kubectl version --client
```
**it checks the version**

### Installing Minikube

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

#
#
```
minikube version
```
**it checks its version**

### Starting Minikube with Docker Driver

```
minikube start --driver=docker
```







**# If you encounter root privileges error, run:**
```
minikube start --driver=docker --force
```

```
minikube status
```
**it checks its status**







```
kubectl cluster-info
```
**it checks cluster info**



```
kubectl config view
```
**it will  show the config**







```
kubectl get nodes
```
**it will display  nodes in it**


```
kubectl get pods
```
**it will show pods in it**


```
kubectl create deployment nginx-web --image=nginx
```
```
kubectl expose deployment nginx-web --type NodePort --port=80
```
```
kubectl get deployment,pod,svc
```
**it will deploy a sample nginx deployment**


```
minikube addons list
```
**It will display all addons**







```
minikube addons enable dashboard
minikube addons enable ingress
```
**this  enables these addons**











```
minikube dashboard --url**
```
**it will get the url and run the dashboard of MiniKube**






```
kubectl proxy --address='0.0.0.0' --disable-filter=true &
```
**This will enable port :8001 to access it on your public ip**






```
http://server_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/workloads?namespace=default
```
### Now go to above link and replace server_ip with your public ip and it will show you like :

![minik8s](https://github.com/user-attachments/assets/f92e7dca-a8c0-4c8e-aae8-4a0c88c5443e)







