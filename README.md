Table of Contents:
  
  
1-[Installing Python on Native Windows](#1)     
2-[Installing Python on WSL Linux](#2)    
3-[Appendix](#3)

&nbsp;

&nbsp;

<a id='1'></a>
<h2>1- <u>Installing Python on Native Windows:</u></h2>



<h4>A- Download the executible package</h4>
 

You can install Python using one of two related sources    

[Miniconda](https://docs.conda.io/en/latest/miniconda.html) (Recommended)     
[Anaconda](https://www.anaconda.com/distribution/)  Miniconda + user iterface (Navigator) 

Miniconda is recommended as it has a lighter footprint on the system. If you wish to install any additional tools such a Spyder or Jupyter Lab you can do so from the command line. 




<h4>B- Start with the conventional installation using Python 3.X. If you use Python 2.7 It can be installed as an additional environment after the installation is complete.</h4>


Make sure you check the box below so that Anaconda/Miniconda is added to your PATH variable and follow the prompts.

Know where your root installation folder is, usually it is <i>C:/Users/Your_User_name/Miniconda3</i>


<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/Python%20PATH%20Env.PNG"  width="500"/>

<br>

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/add%20to%20path%20variable.PNG"  width="500"/>

&nbsp;

<h4>C- Pin the Anaconda prompt to taskbar and start is using <u>Run as administrator</u></h4>

Make this easily accessible as you'll be using it everytime you need to start jupyter  

<u>Going forward always run anaconda prompt as an administrator</u>

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/running_anaconda_prompt_asadmin.PNG"  width="500"/>

&nbsp;


<h4>D- Checking conda environments</h4>
 run the following command,
 `conda info --envs`

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/conda_info_envs.PNG"  width="400"/>

 you should have a single environment after the new fresh install `(base)`
 

<u><i>Ideally you should create a new environment for different projects that you work on. Some packages may have conflicts and you want be minimalistic when it concerns different packages to maintain a light and conflict free environment</u></i>



<h4>E- Creating a new environment</h4>
You can certainly use the _base_ enviornment, but if _base_ gets corrupt that becomes a problem.   
It is recommended that you create your own enviornment following the steps below:   
    
`conda create -n py38 python=3.8`

the name `py38` can be anything of your choice, this is the name of the new enviornment  
<b>(the example show below is for python 3.7, this release is no longer available for Miniconda/Anaconda and is less stable than its predecessors and successors)</b>


&nbsp;


<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/conda_create_n.PNG"  width="600"/>

activate the new environment by running the command: 

`conda activate py38` 

You'll need to switch to this environment everytime you start the Anaconda prompt as it will always revert to `*base` 

&nbsp;


<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/activate_new_env.PNG"  width="600"/>

notice that the prefix now changes form `(base)` to `py37` or `py38`

&nbsp;

<h4>F -Updating and installing new packages</h4>
    
* You can install new packages to your python using two commands `pip` or `conda` indicating which repository you are downloading the packages from. 

* It is always recommended that you install packages using `conda` from the anaconda cloud because the installer will always check for environment inconsistencies before installing a new package. `pip` on the other hand installs everything by brute force. 

You can check what packages you have installed by running the following command(s):

for pip:
`pip list`

for conda:
`conda list`

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/pip_list_conda_list.PNG"  width="500"/>

* <u>updating pip</u>: someitimes pip may not be updated to the very latest version, you may use one of these two commands to update pip itself 
   
`pip install upgrade pip`   
or   
`python -m pip install --upgrade pip`   

* <u>updating jupyter</u>: If you installed python using Miniconda (recommended) you will need to install jupyter and jupyter lab manually using the two following commands:   

`conda install jupyter`   
and   
`conda install jupyterlab` 



&nbsp;


<h4>G- The correct way to start jupyter notebook or jupyter lab</h4>
    
* If you chose to install Anaconda vs. Miniconda then you have the Anaconda Navigator.

<icon src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/stop-sign-png-27231.png"  width="40"/> DO NOT OPEN JUPYTER NOTEBOOK/LAB USING ANACONDA NAVIGATOR

<br>

* It is generally considered bad practice to start jupyter notebook from within the Anaconda Navigator. The power of jupyter is it's ability to be deployed in any folder or remote location, starting jupyter notebook using Anaconda Navigator restricts you to the root installation folder and forces you to place all your files inside the root installation folder, in my case this is <i>C:/Users/Drosophila</i> as you can see in the prompt itself. 

* the ideal way to start jupyter is to navigate to the folder where your project is using the Anaconda prompt (command line) and then starting jupyter notebook or jupyter lab as such

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/open%20jupyter%2002.JPG"  width="900"/>

&nbsp;

&nbsp;

&nbsp;

&nbsp;
<a id='2'></a>
<h2><u>2- Installing Python on Windows Linux using WLS: (THE BEST OPTION)</u></h2>

Windows 10 allows users to install a full version Linux Bash on a windows machine. This is referred to as WLS (Windows Linux Subsystem).   

Python is more stable when installed on Linux then when installed on Windows. For this reason, it is recommended that you install Linux using WLS  (Ubuntu or any other Linux distro of your preference) and then install Python into Linux.    

&nbsp;

<h3>A. Installing WLS on Windows </h3>

* 1-	Search for <b>Turn Windows features on or off</b> in your start menu and when it comes up click it 


<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/turn_on_windows_.jpg"  width="500"/>

* 2-	Check the box for    <b>Windows Subsystem for Linux</b> 

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/activate_WSL.PNG"  width="500"/>

* 3- Open the Microsoft Store and search for your favorite Linux distro

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/search_for_linux.jpg"  width="500"/>

* click the <b>get</b> button

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/finding_linux.jpg"  width="500"/>

Follow the prompts for the linux installation, you'll be prompted to set your username and password   

When the installation is complete check your shell by typing the following command   

`echo $SHELL`

check the weather too while you're at it 

`curl wttr.in/chicago`   

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/checking_shell.png"  width="800"/>

welcome to shell

in shell, root: `/` is the location where your system files are installed 

to access your local drives, aka `C:/` `D:/` etc you need to change director into the folder `/mnt`

&nbsp;


<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/location_of_local_drives.PNG"  width="800"/>


to make these easily accessible create aliases in your `~/.bashrc` file that will point to `/mnt/c` or `/mnt/d`

&nbsp;

<h3>B. Installing Miniconda Python on WSL</h3>

The link recomended above for [Miniconda](https://docs.conda.io/en/latest/miniconda.html) condains the Linux installers   

* 1- download the shell file `Miniconda3-latest-Linux-x86_64.sh`

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/miniconda3_linux.PNG"  width="800"/>

* 2- navigate to the location of `Miniconda3-latest-Linux-x86_64.sh` and run the command   

`sh Miniconda3-latest-Linux-x86_64.sh`

follow the prompts until the installation is concluded and you're back to your open command prompt. 

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/minionda3_shell_install.PNG"  width="800"/>

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
<h2><u>3- Appendix</u></h2>

&nbsp;

<b>1- Installing python packages on a work computer</b>

If you are using a work laptop you may need to use some additional syntax to get across firewalls and security. 

for conda run the following command per session 
`conda config --set ssl_verify FALSE`

for pip which installs from pypi.org repository you may need one or all of the following `--trusted-host` directives   

`pip install --trusted-host pypi.python.org --trusted-host pypi.org --trusted-host files.pythonhosted.org <package name>`     
`pip install --trusted-host pypi.python.org --trusted-host pypi.org --trusted-host files.pythonhosted.org <package name> --upgrade`   


&nbsp;

<b>2- setting up an environment with a different version of python</b>

you might needs to setup a python environemtn with python3.5 needed for work or for a special project, you can specify the version of python as such:

`conda create -n py35 python=3.5`

If you are required to use python 2.7 (usually for work) you can use the following command, also consider looking for a new job.

`conda create -n py27 python=2.7`

the support for python2.7 will cease on Jan-1-2020. 


&nbsp;

<b>3- checking the version of your installations</b>

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

<b>4- modifying Linux `~/.bashrc` file</b>

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

<img src="https://github.com/drosophila/step_by_step_python_installation/blob/master/docs/static/bashrc_shot.PNG"  width="800"/>

* in my command line: 

c ENTER executes `cd /mnt/c`   
x ENTER executes `cd /mnt/x`

&nbsp;

<b>5- famous packages to install</b>

we are going to need these packages in our class   

`echo` is linux for print.   

in linue the pipe operator `|` takes the output from the left side of the argument and pipes it as an input to the right side     

`echo y | conda install -c conda-forge pandas` respones with `y` to the prompt question `proceed [y/n]` and automatically carried out the installation. 

&nbsp;



`echo y | conda install -c conda-forge pandas`   
`echo y | conda install -c conda-forge numpy`   
`echo y | conda install -c conda-forge scikit-learn`    
`echo y | conda install -c conda-forge statsmodels`  
`echo y | conda install -c conda-forge matplotlib`   
`echo y | conda install -c conda-forge seaborn`

&nbsp;

modules that are problematic on Windows but run with no issues on Mac or Linux  

`conda install -c conda-forge pydot`   
`conda install -c conda-forge graphviz`   
