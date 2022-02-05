# installing downloaded ".deb" files
- go to the location where the file is downloaded with the CLI
	- ```cd /path/to/file```
- use the ***dkpg*** command to install the file
- syntax:
	- ```sudo apt install -y [ name_of_package ... ]```
- example:
	- ```root@ubuntu# dkpg -i file_name.deb```


# installing packages from remote software repo
- use the ***apt*** command to install the package
- syntax:
	- ```sudo apt install -y [ name_of_package ... ]```
- example:
	- ```root@ubuntu:# sudo apt install -y vscode```


