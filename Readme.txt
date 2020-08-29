In order to setup a Single node Hadoop cluster you will need a linux box. 
Given below is just one of the many known ways to create a VM on your windows machine. 
You may use this way to create a VM or you may choose to use any other way which you are already comfortable with

Hardware requirements: Minimum 4GB RAM & 10-15 GB space on the HDD
Additional requirements: Reasonably good internet connection. You will be downloading roughly 1 GB of data  

Download and install "Putty" from the following link which is required to connect to a VM which we will create in the steps to follow
http://www.putty.org/

Download and install "WinSCP" from the following link which is required to move files from windows to linux VM and vice-versa
https://winscp.net/eng/download.php

Download and install "Oracle Virtual Box" from the following link. This is the virtualization provider for us
https://www.virtualbox.org/wiki/Downloads

Download and install "VM VirtualBox Extension Pack" from the following link
https://www.virtualbox.org/wiki/Downloads

Download and install "Vagrant" (Desktop Virtualization Software)
https://www.vagrantup.com/downloads.html

You need to enable Virtualization on your laptop\desktop and this is a non-negotiable pre-requisite to create a virtualized environment on your desktop. 
The steps for the same depend on your laptop\desktop model. 
You should take help from Tech Support to do the same if you are not comfortable doing it on your own.

After you have enabled virtualization dont forget to restart your machine

Open a command prompt at the current location ie <<C:\Work>>\HadoopPseudo_Light and type the following command
vagrant up


The step above will take quite some time to complete based on the speed of your internet connection.
Once completed a VM would have been created in your machine with a Hadoop Single node cluster. 
Connect to this VM using putty with the following details

Host Name (or IP address) : 127.0.0.1
Port: 2222

You will be prompted for a user id and password
user ID: vagrant
password: vagrant

Java binaries are @ /home/vagrant/bigdata/java
Hadoop binaries are @ /home/vagrant/bigdata/hadoop
Directories for name node and datanode are @ /home/vagrant/bigdata/hadoop_tmp

--------------------------------------------------------------------------------------------------------------------------------------------------------------
You can choose any editor of your choice to write MapReduce Programs in Java.
If you want to use Maven as your build & dependency management software, the following dependency in your pom.xml should suffice.
	<dependency>

		<groupId>org.apache.hadoop</groupId>
		<artifactId>hadoop-client</artifactId>
		<version>2.7.2</version>
        </dependency>
--------------------------------------------------------------------------------------------------------------------------------------------------------------		
		