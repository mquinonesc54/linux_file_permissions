# linux_file_permissions
Project to showcase how I used chmod in Linux to set permissions for certain directories and files

## Project Description

To ensure a secure system, the research team in my organization must revise the permissions for specific files and directories within the `projects` directory. Currently, these permissions do not align with the appropriate level of authorization. By inspecting and modifying these permissions, we guarantee system security. To accomplish this, I undertook the following steps:

### Check file and directory details

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Screenshot of checking file and directory details](https://i.imgur.com/2HwqNVs.png)

We start off the lab in researcher2’s directory. From there, I use the command ```ls``` to see the files inside of their directory, and it outputs the directory ```projects```.

I then proceed to change the current working directory to the ```projects``` directory using the command ```cd```. Once in the projects directory, I use the command ```ls``` again this time with the options ```-la``` which allows us to see a listed view of the output with things such as file permissions, file size, etc, as well as any hidden files.

The output indicates that there is one directory ```drafts```, one hidden file titled ```.project_x.txt``` and then four other project files.

In the first column, the first 10-strings include the current file permissions for each of the files and one directory.

### Describe the permissions string

The 10-strings each represent permissions of who can authorize certain files and what authorization they may have. The following below explain each of the 10 strings:

- 1st character:
  - This character will be represented by either a ```d``` or a ```-```. A ```d``` will represent a directory and a ```-``` will represent a file.
- 2nd-4th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of the user. If there is a ```-``` instead, this will indicate the user does not have permissions for that field.
- 5th-7th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of the group. If there is a ```-``` instead, this will indicate the group does not have permissions for that field.
- 8th-10th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of other. What that means is this owner type will represent all other users/groups on the system. If there is a ```-``` instead, this will indicate other does not have permissions for that field.
