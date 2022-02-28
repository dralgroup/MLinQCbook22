# Repository for the case studies
Firstly, you need to install git if you are a windows user. (macOS and Linux user already has git installed on their system.)  
To install git, you can check this [website](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for reference.  
But some case study can only be executed on Linux system, So it would be better to perform all the operations on Linux system. 

## Cloning this repository 

### Method 1: pull all the code and data
```shell
git clone ----recursive https://github.com/dralgroup/MLinQC22.git
```

### Mehtod 2: you can pull sub-module later
```shell
git clone https://github.com/dralgroup/MLinQC22.git    # pull this repo without sub-module 
git submodule init      # register sub-module 
git submodule update    # pull sub-module
```

## Updating the sub-module 
If you find some disagreement or incomplete in sub-module, it would be the reason that the original author updated the sub-repo (sub-module), you can enter the directory of that sub-module, then execute `git pull origin main` or `git pull origin master` (if previous command prompts error), if the problem sitll exists, feel free to contact us. 

# How to execute case study 
## jupyter notebook
Most of the case study is writen in jupyter notebook (with the suffix of ".ipynb"), which relys [python](https://www.python.org), so it's highly recommend to install [anaconda](https://anaconda.org) to avoid unnecessary linux environmal problem. (because most of hte software and library are installed in anaconda)

### install necessary software and library if you don't use anaconda
We only list the basic necessary library you need to install, but you may still encountered missing library problem in some cases.
```bash 
pip install jupyter jupyterlab numpy matplotlib scipy
```

### setup jupyter-lab password
```bash
jupyter-lab password
```

### execute *.ipynb in your local workstation/PC
You need to enter case study path, then use command `jupyter-lab`, it will open a webpage, just click "*.ipynb" file to open it, use "SHIFT + ENTER" to execute a cell. 

### execute *.ipynb in Linux server
FIrstly, you need to enter the case study directory,  
Secondly, you need to check whether your Linux server is accessible from your PC, a simple way to check:  
in your server, execute command:
```bash
python3 -m http.server 9999
```
then in your local PC, open the webpage `http://your_server_ip:9999`, if you successfully open it, it means that you can access your server through http from your PC freely.

#### if you can access your server
In your server, execute command 
```bash 
jupyter-lab --ip 0.0.0.0 --port 8888 --no-browser
``` 
then in your PC, visit the webpage `http://your_server_ip:8888`, enter the password to use jupyter-lab

#### if you can not access your server
You need to setup ssh tunnel to visit it.
if your PC OS is macOS or Linux, then execute command in your PC:
```bash
ssh -NL 8888:127.0.0.1:8888 {user}@{server_ip} -p {ssh_port}
```
if your PC OS is Windows, you can setup ssh port-forwarding (tunnel) using ssh software (PuTTY or MobaXterm or Xshell), you need to set: 

> Listen: Local  
> Source port: 8888  
> Destination: 127.0.0.1  
> Destination Port: 8888  

In your server, execute command:
```bash
jupyter-lab --port 8888 --no-browser 
```
In your PC, visite the webpage `http://127.0.0.1:8888`, enter the password to use jupyter-lab

### basic usage in jupyter-lab 
You need to enter case study directory, then use the command introduced above to open jupyter-lab server, and open webpage on local PC, just click "*.ipynb" file to open it, use "SHIFT + ENTER" execute a cell. 

## others
Please read the **README.md** file for more detail. 

