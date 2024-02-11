# AUTOLOADBALANCER


The aim of this project is to automate the process of creating loadbalancer by adopting the use shellscripts. In this case, all the instances and connection to remote system ubuntu will be completed manually but the rest will be completed using automation through shellscripting. 


#### Step - 1 Create two instances.

The image below shows Instance 1 created and named `APACHECLB1`

![alt text](<img/01.in -1 .png>)

The second instance is created and shown below; `APACHELB2`

![alt text](<img/02.in 2.png>)

For the 2 intances, open port 8000 by editing the inbound rules for both, as shown in the images below

![alt text](<img/03.port 1.png>)


![alt text](<img/04.port 2.png>)


#### Step - 3 Connect the instances

Now that all the instances are set up, they will be connected from the local terminal through `SSH` as shown in the images below. it should be noted that the key should be made viewable before connection is attempted.
Here, the key pair is '`loadruner.pem' and the DNS will be used in the command instead of the IP address

The images below show how the connection for both instances are made.

![alt text](img/05.SSH1.png)

![alt text](img/06.SSH2.png)

![alt text](img/07.con1.png)

![alt text](img/08.con2.png)


#### Step - 4 Deploy and configure the webservers

Here a shellscript will be used to complete the process of installing apache and configuring the ports.configuration. To achieve this a `.sh` file will be created and edited to contain the shellcript and executed, as shown in the images below. These will be done for each instance separately.

![alt text](<img/09.vi 1.png>)

![alt text](img/10.scipt1.png)

![alt text](<img/13.vi 2.png>)

![alt text](img/14.script2.png)

Now that the scripts are saved in `install.sh` file, ownership/permission will be granted before the scripts can be executed 

The images below show the execution and results for both instances 


![alt text](<img/11.run 1.png>)

![alt text](<img/12.run 1-1.png>)

![alt text](<img/15.run 2.png>)

![alt text](<img/16.run 2-2.png>)


The above shows that both webservers are now active.


#### Step - 5 Deploy and configure NGINX Loadbalancer

Now an additional instance will be created and it port will be ameneded to allow traffic from anywhere through port 80.

The images below show the new instance and port

![alt text](<img/17.inst -ng.png>)

![alt text](img/18.port-ng.png)

once the instance is created, it is connected via SHH as shown below

![alt text](img/19.ssh-ng.png)

![alt text](<img/20.con -ng.png>)

After the connection is completed, the NGINX Loadbalancer will be deployed and configured automatically through shellcript. To achive this a file names nginx.sh is created and amended to contain the executable script. This will be run to deploy and configure NGINX as loadbalancer as shown in the images below

![alt text](img/21.script-ng.png)

![alt text](<img/22.run -ng.png>)

![alt text](<img/23.run -ng2.png>)

#### Step - 6 Verifying the set up

Once the above have been completed successfully, verify the webservers and NGINX loadbalancer  work as they should by typying their IP addresses in the browser. Each webservers should its IP address and the NGINX will show the IP address of the webserver as shown in the images below.



![alt text](img/25.wel-83.png)

![alt text](img/26.wel-87.png)

![alt text](img/27.wel-ng.png)

