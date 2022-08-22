# Applied Operations Research
Since you are reading this file, you were able to log in and to reach the JupyterLab. 
This file shows you how to setup your environment for the course.

The first time you log in to JupyterLab you need to prepare the environment for your work during the rest of the course. Fortunately, things are not too difficult to do. Most of the work consists of setting Gurobi and its license up and running. These are the tasks
- Go to this link https://www.gurobi.com/academia/academic-program-and-licenses/, sign up with you KU email, and follow the Web License Service (WLS) instructions to obtain a license.
- Go to https://license.gurobi.com/manager/keys/ and create an API key for your WLS license. This API key will allow you to use your license on JupyterLab. Give the key an informative name (just in case you will have multiple keys in the future). Then, download the API key at the time you create it (OBS! this is the only time you can access it directly). The download button downloads a license file `gurobi.lic` which looks like the following 
```
# Gurobi WLS license file
# Your credentials are private and should not be shared or copied to public repositories.
# Visit https://license.gurobi.com/manager/doc/overview for more information.
WLSACCESSID=**********************
WLSSECRET=************************
LICENSEID=******
```
- Create a folder on your ERDA account where you will store all your AOR files.
- Create a `gurobi.env`  file on ERDA. The file should be like [this](./gurobi.env). You simply need to put the right values for the `WLSACCESSID`, `WLSSECRET`, and `LICENSEID`. All this information is in your `gurobi.lic` file. Note that the `gurobi.env` file should **always** be in the same folder as the notebooks that use Gurobi. Therefore, it is probably a good idea to create a subfolder named, for example, `gurobi_models` where you will collect, from a week to another, all your Gurobi work, and put the `gurobi.env` file in that folder. In this way you do not have to copy the license file around every time.
- Activate the python3 environment by running ``conda activate python3``
- Install Gurobi on your environment by running ``pip install --user gurobipy``  (note that the flag `--user` is important as it make the installation permanent, otherwise you need to install it every time you start your environment).

Your initial setup is now complete! To test your installation, open and run the Jupyter notebook called `diet_problem` which you find in the same folder as this file. Particularly, you should see an output similar to this 

```
Set parameter WLSAccessID
Set parameter WLSSecret
Set parameter LicenseID
Academic license - for non-commercial use only - registered to gp@math.ku.dk
Gurobi Optimizer version 9.5.1 build v9.5.1rc2 (linux64)
..... CONTENT OMITTED
Solved in 3 iterations and 0.05 seconds (0.00 work units)
Optimal objective  1.237704918e+02
Objective value: 123.77
xa 0
xb 0
xc 16.6667
xd 0
xe 4.91803
```
The two important pieces of information here are 
1. that you find a solution at the bottom of the output. This means that Gurobi has been installed succesfully
2. that you read your email at the top of the output in the license information. This means something like `Academic license - for non-commercial use only - registered to gp@math.ku.dk`.

You are ready to work on your notebooks!

## Every time you start your Jupyter service
- In the Launcher, open the terminal and activate the python3 environment by running the command line instruction ``conda activate python3``