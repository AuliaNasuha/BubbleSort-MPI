# BubbleSort-MPI With Python
This repository will discuss how to install MPI and how to execute the Buble Sort Python program using Ubuntu Server 22.04 as the operating system used.

# Installation MPI On Ubuntu Server
## Topologi
![image](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/f8d0a758-04d8-4092-b9a8-b7510e6e417a)

## 1. First Step
1. Set up several computers and designate one computer as the master and several computers as slaves.
2. Make sure all computers are connected to one network.
3. Update and Upgrade package **sudo apt update && sudo apt upgrade**

## 2. Make A New User
Do it on Master And Slave
1. Create User <br> **sudo adduser <nama user>**
2. Give a Access Root <br> **sudo usermod -aG mpiuser**
3. Sign Into New User <br> **su - mpiuser**

## 3. Install MPICH
Do it on Master and Slave
1. Install MPICH And All Documentation Mpi <br> **sudo apt-get install -y mpich-doc mpich**
2. Check Version Of MPI <br> **mpirun --version**
3. Testing The Installation <br> **mpiexec -n <jumlah core> pyhton3 -m mpi4py.bench helloworld**
4. Install packet python mpi4py with pip to run python on MPI <br> **pip install mpi4py -U**

## 4. Configuration File /etc/hosts
**sudo nano /etc/hosts**
1. Master <br>
   ![image1](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/4eebb045-9e2d-4c10-abc1-8cf37bb57704)
2. Slave <br>
   ![Image2](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/1b49e18a-57ec-4284-8dac-daf4ef5a97d6)

## 5. Install SSH
Do It On Master And Slave <br>
**sudo apt install openssh-server**
1. make a Key <br> On Master **ssh-keygen -t rsa**
2. Copy key public to client <br> **ssh-copy-id <user>@<host>** <br>
   Change <user> to user we make it and <host> to slave, do it to all slave.

## 6. Run MPI
Do it on master <br> **mpiexec -n <Numbers Of core> python -m mpi4py.bench helloworld**<br>
<img width="404" alt="percobaan" src="https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/8e1d12c1-2d12-4016-afd9-341b1eea56e7">

# How Run Bubblesort MPI With MultiNode
## 1. Copy id Master To All Slave 
**ssh-copy-id user@hostname_or_ip**

## 2. Making Program BubleSort Python 
The Code Of BubbleSort <br>
![G2](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/06f0602c-f77c-4e96-a9cc-2bcae83c3c68)

## 3. Copy File Python on All Slave
**~path$ scp /path/to/locate/bin * user@hostname_or_ip:path/to** <br>
![image](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/d6455bd1-4c86-41e2-9116-f5648166b92c)

## 4. Output
![image](https://github.com/feliana444/Eksekusi-Program-Buble-Sort-Python-Menggunakan-MPI/assets/145323449/72d92ade-9125-4b55-b043-add4c0e6ee1f)

