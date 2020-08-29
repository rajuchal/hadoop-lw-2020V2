## Automated Setup & Installation Guide for Hadoop Single Node Cluster Environment (Pseudo Distributed mode)
## using light-weight script with Spark/Kafka/Cassandra/MongoDB

### Single Node _Hadoop/Spark/HBase/Kafka/Cassandra/MongoDB_ Cluster on Windows using virtualization

Automation Script for creating single node _hadoop/spark/kafka/cassanda/mongodb_ cluster on Windows 
using Vagrant & Oracle Virtual Box 

### Note :- To run this script, "Virtualization" property should be enabled for the Desktop/Laptop with Admin right

## Connection architecture

**Windows Environment --> Oracle Virtual Box --> Linux Environment**

## Functions of the template & script -
1. Install Hadoop stack, Spark, Kafka, Cassandra, MongoDB into Linux VM

## Pre-requisite Software
### Download & Install the following software on Windows before running the script

1. Download and Install Oracle Virtual Box
   	
	https://download.virtualbox.org/virtualbox/5.2.38/VirtualBox-5.2.38-136252-Win.exe

2. Download and Install Vagrant version 2.2.4
  
	https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.msi
  
  _After vagrant installation , restart the system _
	
3. Download SmarTTY

	https://sysprogs.com/SmarTTY/download/
	
	OR
	
	Download MobaXTerm
	
	https://mobaxterm.mobatek.net/download-home-edition.html

4. Download WinSCP

	https://winscp.net/eng/download.php
	

	
### ===============================================================
##  INSTALLATION PROCESS
### ===============================================================

#### Pre-requisite :- During entire installation procedure your Laptop/Desktop should be connected with Internet.
#### Minimum RAM Required :- 8 GB

1)  Unzip the file in C-Drive
2)	Open the Windows Command Prompt
3)	Go within the "extracted folder/HadoopPseudo_Light....." directory in the Command Prompt
4)	Run “setup.cmd”

C:\HadoopPseudo_Light-2020v1> setup.cmd

		------------- Wait till you getback the Command Prompt
		------------- Depending on the bandwidh total installation may take 45 mins to 1 hr time

5) After getting back the Command Prompt type "vagrant ssh" to login to Linux Box

C:\HadoopPseudo_Light-2020v1>vagrant ssh

vagrant@master:~$ jps
11538 Jps
9716 DataNode
9942 SecondaryNameNode
10520 Master
9528 NameNode
10107 ResourceManager
10446 NodeManager
10750 Worker
vagrant@master:~$

------------------------------------------------------
=========================================================
USE SmarTTY/MobaXTerm/ WinSCP to Connect with the Linux Node


============================================================


Happy Clustering 

=============================================================================
1. Open Azure Portal   [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/)

2. Open Power Shell in Aazure Portal
3. Download the Power shell script 

    #### wget https://raw.githubusercontent.com/rajuchal/multiuser_env_template/master/template-script/create-multiuser-env.ps1

4. Download the ARM template file & template parameter file

    #### wget  https://raw.githubusercontent.com/rajuchal/multiuser_env_template/master/template-script/multiuser-multinsg-template.json
    
    #### wget https://raw.githubusercontent.com/rajuchal/multiuser_env_template/master/template-script/multiuser.parameters.json
    #### dir

    ##### Check the template file "multiuser-multinsg-template.json" location
    ##### Check the parameter file "multiuser.parameters.json" location

5. Run the Power shell script

    ##### PS/home/USER_NAME>./create-multiuser-env.ps1
         **Example**
         Enter the same project name: lkm_dna_env
         Enter the full path of template file location: ./multiuser-multinsg-template.json
         Enter the full path of parameter file location: ./multiuser.parameters.json
         Enter the number of Users: 3
        
6. After script execution completed, Connect Windows VM using RDP
7. Check the location *"C:\windowsTools"* for Windows Tools (SSH Clients & Browser)
   - Unzip MobaXTerm or SmarTTY
   - Connect with Linux VM using SSH connection
   - IP Address for Linux VM - 10.1.2.4
   - Use same User Name & Password of Windows for Linux VM Log-in 

8. Start Hadoop Services in Linux VM
    ##### $ start-dfs.sh
    ##### $ start-yarn.sh

9. Start Spark Services in Linux VM
    ##### $ start-master.sh
    ##### $ start-slaves.sh

10. Start Spark(Scala/Java) Shell  in Linux VM

    ##### $ spark-shell --master spark://localhost:7077

11. Start Spark(Python) Shell  in Linux VM

    ##### $ pyspark --master spark://localhost:7077

12. Start Hive  in Linux VM

    ##### $ hive

### *Note-*
#### Installation directory in Linux VM - /app/bigdata
#### Default user name for Windows & Linux VM - azureuser
#### Default password for Windows & Linux VM - Password@1234

:+1: **_Happy Clustering in Azure_** :shipit:
