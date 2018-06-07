# cise-corr-2017-usecase
This repository contains all the material for the use case of CiSE paper about CoRR.
For each subfolder you will have to do the following commands for each Tool.
All this was done with python 3.5.

## Config from CoRR
First create an account in CoRR.
Then go to your Dashboard.
In the tools credentials download the config files for:
Sumatra: Sumatra-config.json
ReproZip: Reprozip-config.json
CDE: CDE-config.json
Create a folder corr-configs somewhere easy to find using a fullpath.
Usually your home directory is a good place to start.
In Ubuntu it's /home/username, in MacOSX /Users/username.
Sadly i am not a windows expert. I am open to contributions.
create three subdirectories: smt, rpz, cde
In each copy and rename the config file to config.json in the correct folder.
For example Sumatra-config.json goes in */corr-configs/smt/config.json.
Now your tools credentials are ready to be used.

## Install the tools
Make sure you have git installed.
All the three tools codes can be found at [https://github.com/usnistgov/](https://github.com/usnistgov/)
They are respectively named: corr-sumatra, corr-reprozip, corr-cde.
Before attempting any installation we recommend installing an environment manager tool such as
Anaconda, PyEnv or VirtualEnv. This allows a cleaner test.
Create a folder corr-tools that will contains all the tools codes to be installed.
Now clone the codes using for example for corr-reprozip:
	
	git clone git@github.com:usnistgov/corr-reprozip.git

After cloning the tools codes in corr-tools folder.
Activate the environment in which you wish to install the tools.
For corr-sumatra, do:

	python setup.py install
	pip install gitpython

The extra installations are dependencies needed by Sumatra.
To validate the installation, make sure you can run:

	 smt

For corr-reprozip, first go to the reprozip subdirectory and do:
	
	python setup.py install

To validate the installation, run: 

	reprozip

For corr-cde, do
	
	python setup.py install

To validate the installaton, run:

	corrcde

In case of an issue it is possible the cde command is not built, run:

	make install

Before you continue to run the use examples, make sure you are
still within the environment in which you installed the tools.

## Using Sumatra
First check that the source code has not changed:
	
	git status

If so, you will have to commit your changes:

	git add files...
	git commit -m "Message..."

After making sure the code is commited, initialize Sumatra:

	smt init -s path_to/corr-configs/smt/config.json Project_Name

Then configure the execution:

	smt configure --executable=python --main=code_example.py

Finally to run the code with Sumatra:

	smt run

At this point you have to wait for the computation to finish.
Check in CoRR from time to time to see the computation record.

## Using Reprozip
It is pretty straighforward.
There is no need to worry about version control.
In the Reprozip jargon, to trace a code you have to do:

	reprozip trace -config=path_to/corr-configs/rpz/config.json -name=Project_Name python code_example.py

At this point you have to also wait for the computation to finish.

## Using CDE
It is as easy as Reprozip to use CDE.
To do so, run:
	
	corrcde --config path_to/corr-configs/cde/config.json --name Project_Name --cmd="python code_example.py"

At this point again you have to wait the computation to finish.

## Note
Make sure you have an allowance of about 20Gb. 
This use case execution requires this amount of storage.
The default account is provided with 1Gb.
To validate the use case, first focus on running the simple examples.
They are: Perceptron-And/Xor/Or and NN-Xor. They require from less storage.
The default storage of 1G can handle these computation with NN-MNIST possibly.
It will not handle the Keras library based examples.
In any case email the instance Admin at yannick.congo@gmail.com to request a storage
increase for [https://corr-root.org](https://corr-root.org).

## Caution
This instance is experimental, please inquire about your actual use cases to
request either for extra storage or to see if it fits within the scope of the instance.
There no official financial support for this instance, the admin is paying for the infrastructure.
A donation button has been provided for contributions to help pay these costs.

## Credit
All these codes are taken from Dr. Adrian Rosebrock book on Deep Learning For Computer Vision with Python.
For further interest and understanding, we recommand buying a copy of this trending book on Artificial Neural Networks. 
