# Operating-Systems-Linux-Basics

## EXERCISE 1: Linux Mint Virtual Machine

### Which package manager is installed by default:

* APT

### Which CLI editor is installed by default?:

* Vim
* Nano

### Which shell is configured?:

* BASH


## EXERCISE 2: Bash Script - Install Java

```bash
#!/bin/bash

sudo apt update
sudo apt install default-jdk

version_info=$(java -version 2>&1)


version=$(echo "$version_info" | grep 'version' | awk -F '"' '{print $2}')


echo "Java successfully installed at version: $version"


installed_version=$(echo "$version" | cut -d '.' -f 1)


if [ "$installed_version" -lt 11 ]; then
    echo "Installed version is lower than v.11. Installing higher version!"
    sudo apt update
    sudo apt install openjdk-17-jdk
else
    echo "Installed version is $installed_version or higher. Installation successful!"
fi


```


## EXERCISE 3: Bash Script - User Processes



```bash

#!/bin/bash

# Get the current user's username
user=$USER

# Print a message indicating the processes being checked
echo "Checking processes for user: $user"

# List all processes for the current user
output=$(ps aux | grep "$user")

# Print the output and a message indicating the end of the process list
echo $output
echo "Process listing complete."


```

























