Table of Contents:
  
  
1-[Installing Python on Native Windows](#1)     
2-[Installing Python on WSL Linux](#2)    
3-[Appendix](#3)

&nbsp;

&nbsp;

<a id='1'></a>
## 1- <u>Installing Python on Native Windows:</u>



#### <span style="color:red">A- Download the executible package</span>   

You can install Python using one of two related sources    

[Miniconda](https://docs.conda.io/en/latest/miniconda.html) (Recommended)     
[Anaconda](https://www.anaconda.com/distribution/)  Miniconda + user iterface (Navigator) 

Miniconda is recommended as it has a lighter footprint on the system. If you wish to install any additional tools such a Spyder or Jupyter Lab you can do so from the command line. 



#### <span style="color:red">B- Start with the conventional installation using Python 3.X. If you use Python 2.7 It can be installed as an additional environment after the installation is complete.</span>

Make sure you check the box below so that Anaconda/Miniconda is added to your PATH variable and follow the prompts.

Know where your root installation folder is, usually it is <i>C:/Users/Your_User_name/Miniconda3</i>


<img src="Python PATH Env.PNG" alt="Drawing" style="width: 500px;"/>

<img src="add to path variable.PNG" alt="Drawing" style="width: 500px;"/>

&nbsp;

#### <span style="color:red">C- Pin the Anaconda prompt to taskbar and start is using <u>Run as administrator</u></span>

Make this easily accessible as you'll be using it everytime you need to start jupyter  

<u>Going forward always run anaconda prompt as an administrator</u>

<img src="running_anaconda_prompt_asadmin.PNG" alt="Drawing" style="width: 500px;"/>

&nbsp;


#### <span style="color:red">D- Checking conda environments</span>
 run the following command,
 `conda info --envs`

<img src="conda_info_envs.PNG" alt="Drawing" style="width: 400px;"/>

 you should have a single environment after the new fresh install `(base)`
 

<u><i>Ideally you should create a new environment for different projects that you work on. Some packages may have conflicts and you want be minimalistic when it concerns different packages to maintain a light and conflict free environment</u></i>



#### <span style="color:red">E- Creating a new environment</span>
You can certainly use the _base_ enviornment, but if _base_ gets corrupt that becomes a problem.   
It is recommended that you create your own enviornment following the steps below:   
    
`conda create -n py38 python=3.8`

the name `py38` can be anything of your choice, this is the name of the new enviornment  
<b>(the example show below is for python 3.7, this release is no longer available for Miniconda/Anaconda and is less stable than its predecessors and successors)</b>


&nbsp;


<img src="conda_create_n.PNG" alt="Drawing" style="width: 600px;"/>

activate the new environment by running the command: 

`conda activate py38` 

You'll need to switch to this environment everytime you start the Anaconda prompt as it will always revert to `*base` 

&nbsp;


<img src="activate_new_env.PNG" alt="Drawing" style="width: 600px;"/>

notice that the prefix now changes form `(base)` to `py37` or `py38`

&nbsp;

#### <span style="color:red">F -Updating and installing new packages</span>
    
* You can install new packages to your python using two commands `pip` or `conda` indicating which repository you are downloading the packages from. 

* It is always recommended that you install packages using `conda` from the anaconda cloud because the installer will always check for environment inconsistencies before installing a new package. `pip` on the other hand installs everything by brute force. 

You can check what packages you have installed by running the following command(s):

for pip:
`pip list`

for conda:
`conda list`

<img src="pip_list_conda_list.PNG" alt="Drawing" style="width: 500px;"/>

* <u>updating pip</u>: someitimes pip may not be updated to the very latest version, you may use one of these two commands to update pip itself 
   
`pip install upgrade pip`   
or   
`python -m pip install --upgrade pip`   

* <u>updating jupyter</u>: If you installed python using Miniconda (recommended) you will need to install jupyter and jupyter lab manually using the two following commands:   

`conda install jupyter`   
and   
`conda install jupyterlab` 



&nbsp;


#### <span style="color:red">G- The correct way to start jupyter notebook or jupyter lab</span>
    
* If you chose to install Anaconda vs. Miniconda then you have the Anaconda Navigator.

<img src="stop-sign-png-27231.PNG" alt="Drawing" style="width: 40px; vertical-align:middle"/>  DO NOT OPEN JUPYTER NOTEBOOK/LAB USING ANACONDA NAVIGATOR

* It is generally considered bad practice to start jupyter notebook from within the Anaconda Navigator. The power of jupyter is it's ability to be deployed in any folder or remote location, starting jupyter notebook using Anaconda Navigator restricts you to the root installation folder and forces you to place all your files inside the root installation folder, in my case this is <i>C:/Users/Drosophila</i> as you can see in the prompt itself. 

* the ideal way to start jupyter is to navigate to the folder where your project is using the Anaconda prompt (command line) and then starting jupyter notebook or jupyter lab as such

<img src="open jupyter 02.JPG" alt="Drawing" style="width: 900px;"/>

&nbsp;

&nbsp;

&nbsp;

&nbsp;
<a id='2'></a>
## <u>2- Installing Python on Windows Linux using WLS: (THE BEST OPTION)</u>

Windows 10 allows users to install a full version Linux Bash on a windows machine. This is referred to as WLS (Windows Linux Subsystem).   

Python is more stable when installed on Linux then when installed on Windows. For this reason, it is recommended that you install Linux using WLS  (Ubuntu or any other Linux distro of your preference) and then install Python into Linux.    

&nbsp;

### A. Installing WLS on Windows 

* 1-	Search for <b>Turn Windows features on or off</b> in your start menu and when it comes up click it 


<img src="turn_on_windows_.jpg" alt="Drawing" style="width: 500px;"/>

* 2-	Check the box for    <b>Windows Subsystem for Linux</b> 

<img src="activate_WSL.PNG" alt="Drawing" style="width: 500px;"/>

* 3- Open the Microsoft Store and search for your favorite Linux distro

<img src="search_for_linux.jpg" alt="Drawing" style="width: 500px;"/>

* click the <b>get</b> button

<img src="finding_linux.jpg" alt="Drawing" style="width: 500px;"/>

Follow the prompts for the linux installation, you'll be prompted to set your username and password   

When the installation is complete check your shell by typing the following command   

`echo $SHELL`

check the weather too while you're at it 

`curl wttr.in/chicago`   

<img src="checking_shell.png" alt="Drawing" style="width: 800px;"/>

welcome to shell

in shell, root: `/` is the location where your system files are installed 

to access your local drives, aka `C:/` `D:/` etc you need to change director into the folder `/mnt`

&nbsp;


<img src="location_of_local_drives.PNG" alt="Drawing" style="width: 800px;"/>


to make these easily accessible create aliases in your `~/.bashrc` file that will point to `/mnt/c` or `/mnt/d`

&nbsp;

### B. Installing Miniconda Python on WSL

The link recomended above for [Miniconda](https://docs.conda.io/en/latest/miniconda.html) condains the Linux installers   

* 1- download the shell file `Miniconda3-latest-Linux-x86_64.sh`

<img src="miniconda3_linux.PNG" alt="Drawing" style="width: 800px;"/>

* 2- navigate to the location of `Miniconda3-latest-Linux-x86_64.sh` and run the command   

`sh Miniconda3-latest-Linux-x86_64.sh`

follow the prompts until the installation is concluded and you're back to your open command prompt. 

<img src="minionda3_shell_install.PNG" alt="Drawing" style="width: 800px;"/>

* create a new environment:
    
`conda create -n py38 python=3.8`

* switch to the new environment:

`source activate py38`   (this is different than Anaconda prompt)   
  
* install jupyter

`conda install jupyter`  
`conda install jupyterlab`   
    
* update pip

`pip install upgrade pip`   
or   
`python -m pip install --upgrade pip`  

&nbsp;

&nbsp;
<a id='3'></a>
## <u>3- Appendix</u>

&nbsp;

<b><span style="color:blue">1- Installing python packages on a work computer</span></b>

If you are using a work laptop you may need to use some additional syntax to get across firewalls and security. 

for conda run the following command per session 
`conda config --set ssl_verify FALSE`

for pip which installs from pypi.org repository you may need one or all of the following `--trusted-host` directives   

`pip install --trusted-host pypi.python.org --trusted-host pypi.org --trusted-host files.pythonhosted.org <package name>`     
`pip install --trusted-host pypi.python.org --trusted-host pypi.org --trusted-host files.pythonhosted.org <package name> --upgrade`   


&nbsp;

<b><span style="color:blue">2- setting up an environment with a different version of python</span></b>

you might needs to setup a python environemtn with python3.5 needed for work or for a special project, you can specify the version of python as such:

`conda create -n py35 python=3.5`

If you are required to use python 2.7 (usually for work) you can use the following command, also consider looking for a new job.

`conda create -n py27 python=2.7`

the support for python2.7 will cease on Jan-1-2020. 


&nbsp;

<b><span style="color:blue">3- checking the version of your installations</span></b>

run the following two commands:


```python
import IPython 
IPython.__version__
```




    '7.13.0'




```python
import sys
sys.version
```




    '3.8.2 | packaged by conda-forge | (default, Apr 16 2020, 18:04:51) \n[GCC 7.3.0]'



&nbsp;

<b><span style="color:blue">4- modifying Linux `~/.bashrc` file</span></b>

* <b>.bashrc</b> is a hidden file that lives in your home directory     
* this is the first shell script that gets executed whenever you start your shell window    
* if you modify this file you can re-initialize it by running the command `source ~/.bashrc`   
* modifying this file and adding aliases and other lines to exeucte upon start makes your life easier    
* the easiest way to access .bashrc is to execute the commane `vim ~/.bashrc`. The `~` references your home directory, so no matter what folder you're currently in you can can access .bashrc.    
* `vim` is the one of the oldest and most efficient and widely used advanced text editors avaiable and it comes readily installed as part of your Linux/Bash repo. However `vim` has special commands to allow data entry and manipulation using the keyboard only.   
* when you view anything using `vim` it will hijack your bash and your command line will be gone. You will be in read-only mode.   
* to allow keyboard entry to a file being viewed i vim, hit `i` on your keyboard. Now using page-up , page-down navigate and insert commands to execute.      
* when you are done entering commands hit ESC. Now you're back to read-only monde.          
* to quit `vim` use `:q` (quit without saving) or `:qw` (save and quit)       
* an `alias` is a command that allows you to run a another command using a keyword.   
     here's a sample for what an alias in <b>.bashrc</b> looks like    

<img src="bashrc_shot.PNG" alt="Drawing" style="width: 800px;"/>

* in my command line: 

c ENTER executes `cd /mnt/c`   
x ENTER executes `cd /mnt/x`

&nbsp;

<b><span style="color:blue">5- famous packages to install</span></b>

we are going to need these packages in our class   

`echo` is linux for print.   

in linue the pipe operator `|` takes the output from the left side of the argument and pipes it as an input to the right side     

`echo y | conda install -c anaconda pandas` respones with `y` to the prompt question `proceed [y/n]` and automatically carried out the installation. 

&nbsp;



`echo y | conda install -c anaconda pandas`   
`echo y | conda install -c anaconda numpy`   
`echo y | conda install -c anaconda scikit-learn`    
`echo y | conda install -c anaconda statsmodels`  
`echo y | conda install -c anaconda matplotlib`   
`echo y | conda install -c anaconda seaborn`

&nbsp;

modules that are problematic on Windows but run with no issues on Mac or Linux  

`conda install -c anaconda pydot`   
`conda install -c anaconda graphviz`   