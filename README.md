# Install-ROS-noetic

## Definitions :

- VitualBox -> is a free and open-source virtualization software that allows users to create and run virtual machines on their host operating systems. It enables running multiple guest operating systems (OSes) simultaneously on a single physical machine. This virtualization technology is useful for testing software on different operating systems, running legacy applications, and isolating environments for development and experimentation purposes.
- Ubuntu ->  is a popular open-source Linux distribution (OS) based on Debian. It is known for its ease of use, robustness, and community support.It offers a desktop environment that is user-friendly and comes with a variety of pre-installed software, including web browsers, office productivity suites, and multimedia applications. Ubuntu also benefits from a vast repository of software packages that can be easily installed via its package management system.
- Robot Operating System (ROS or ros) -> is a flexible framework for writing robot software. It is a collection of software libraries and tools designed to help developers create complex and robust robot applications. ROS provides functionality such as hardware abstraction, low-level device control, message-passing between processes, and package management. It simplifies the process of creating and managing robot software by providing a standardized and modular approach.

## Steps to install ROS (Robot operating system):
1- Download [VirtualBox](https://www.virtualbox.org/wiki/Downloads) ![Screenshot 2024-07-08 213409](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/91e57b56-7862-4fee-974f-9f28bd532807) 
> [!NOTE]
> Choose your operating system to download the VirtualBox here I choosed Windows host.
<br>

2- Download [Ubuntu 20.04 desktop image](https://releases.ubuntu.com/20.04/) 
![Screenshot 2024-07-08 214252](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/c6705bc6-8844-4d47-a785-ebb3886c4aca)

3- After downloading the VirtualBox and Ubuntu open the  VirtualBox ![Screenshot 2024-07-08 214431](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/59c7bfdc-7a8c-4ba6-b9a1-c325a6021b07) then select New as shown in the photo and follow the next photos
![Screenshot 2024-07-08 215038](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/25324031-59a1-42ac-9146-ad9fbb238ce7)
fill the Name and choose the Type and the Version
![Screenshot 2024-07-08 215136](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/c0ad23e5-037d-4aad-8ad4-a4fe8dc3d1e4)
![Screenshot 2024-07-08 215231](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/45ff7035-82f7-499b-adfb-fdb94412e1a7)
> [!IMPORTANT]
> Select the memories as shown in the photos The Base memory is 4096 MB and The Disk size is 30 GB


![Screenshot 2024-07-08 215313](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/3f0893c2-f340-4538-a3b5-a39dda60a82f)
press Finish then there few steps remain to upload Unbunt as follows
![Screenshot 2024-07-08 220626](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/e5fa9b47-11fd-46d6-b0dd-5f9ceb2d3e93)
press on the Setting then choose Storage
![Screenshot 2024-07-08 215353](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/d8e55815-d618-4446-9d1b-35e6ad91cfdc)
choose the disk as in the photo
![Screenshot 2024-07-08 220819](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/4cf13add-8888-4722-8f92-f44b8fba792f)
then choose a disk file.

4- Now you are ready to start ![Screenshot 2024-07-08 221747](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/4cb8fbc4-95c1-4fa6-83b4-8d8742485a71)
press Start or Ubuntu as shown then choose Install and fill your information.

5- Open the Terminal  
![Screenshot 2024-07-08 222308](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/09a16793-4891-4a6f-8e86-4a4a1b9f1dc2)

6- Write down the following command or vist [Wiki ROS](http://wiki.ros.org/ROS/Installation) for more information<br>

6.1 **Setup your sources.list**
Setup your computer to accept software from packages.ros.org.
~~~ Linux
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
~~~

6.2 **Set up your keys**
~~~ Linux
sudo apt install curl 
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
~~~

6.3 **Installation**
First, make sure your Debian package index is up-to-date:
~~~ Linux
sudo apt update
~~~

then we will Install Desktop-Full: Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages
~~~ Linux
sudo apt install ros-noetic-desktop-full
~~~

6.4 **Environment setup**
You must source this script in every bash terminal you use ROS in.
~~~ Linux
source /opt/ros/noetic/setup.bash
~~~
It can be convenient to automatically source this script every time a new shell is launched. These commands will do that for you.

Bash
> [!CAUTION]
> If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using.
~~~ Linux
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
~~~

6.5 **Dependencies for building packages**
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, [rosinstall](https://wiki.ros.org/rosinstall) is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.<br>
To install this tool and other dependencies for building ROS packages, run:
~~~ Linux
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
~~~

6.5.1 **Initialize rosdep**
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.
~~~ Linux
sudo apt install python3-rosdep
~~~
With the following, you can initialize rosdep.
~~~ Linux
sudo rosdep init
rosdep update
~~~

Finally to Start the ROS (master node)
~~~ Linux
roscore
~~~
![Screenshot 2024-07-07 091532](https://github.com/RaghadAlmadani/Install-ROS-noetic-/assets/173769867/084e4492-e71e-45f4-80f4-0e849a757fb6)
