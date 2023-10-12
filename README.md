# linux_file_permissions
Project to showcase how I used chmod in Linux to set permissions for certain directories and files for my imaginary organization.

## Project Description

To ensure a secure system, the research team in my organization must revise the permissions for specific files and directories within the `projects` directory. Currently, these permissions do not align with the appropriate level of authorization. By inspecting and modifying these permissions, we guarantee system security. To accomplish this, I undertook the following steps:

### Check file and directory details

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Screenshot of checking file and directory details](https://i.imgur.com/2HwqNVs.png)

We start off the lab in researcher2’s directory. From there, I use the command ```ls``` to see the files inside of their directory, and it outputs the directory ```projects```.

I then proceed to change the current working directory to the ```projects``` directory using the command ```cd```. Once in the projects directory, I use the command ```ls``` again this time with the options ```-la``` which allows us to see a listed view of the output with things such as file permissions, file size, etc, as well as any hidden files.

The output indicates that there is one directory ```drafts```, one hidden file titled ```.project_x.txt``` and then four other project files.

In the first column, the first 10 strings include the current file permissions for each of the files and one directory.

### Describe the permissions string

The 10 strings each represent permissions of who can authorize certain files and what authorization they may have. The following below explain each of the 10 strings:

- 1st character:
  - This character will be represented by either a ```d``` or a ```-```. A ```d``` will represent a directory and a ```-``` will represent a file.
- 2nd-4th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of the user. If there is a ```-``` instead, this will indicate the user does not have permissions for that field.
- 5th-7th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of the group. If there is a ```-``` instead, this will indicate the group does not have permissions for that field.
- 8th-10th characters:
  - These characters in this row represent the permissions as follows: read (```r```), write (```w```), and execute (```x```) for the permissions of others. What that means is this owner type will represent all other users/groups on the system. If there is a ```-``` instead, this will indicate other does not have permissions for that field.

Upon taking a look at the screenshot from the [“check file and directory listing”](https://github.com/mquinonesc54/linux_file_permissions/tree/main#check-file-and-directory-details) segment, we can take a look at the permissions for ```project_t.txt```. The permissions are as follows: ```-rw-rw-r--```.

The first character is a ```-```, indicating it is a file. Next, the 2nd-4th characters give the permissions for the owner of the file, in this case, the owner of the file can read (```r```), write (```w```), but not execute (```x```) as indicated by the ```-```.  Then, the 5th-7th characters represent the group file permissions. The group can read (```r```), write (```w```), but not execute (```x```) as indicated by the -. Lastly, the 8th to 10th characters represent the others. The others group only has read (```r```) permissions.

### Change file permissions

The organization has stated that they do not want to allow the others group to have write access to any of the files. 

![Screenshot of the current file permissions](https://i.imgur.com/riBptHP.png)

As shown above, the only file that the others group can write on is the file ```project_k.txt```. In order to remove their write access, I will be using the command ```chmod``` which allows me to change file permissions of directories and files. 

Inputting the full command and arguments I will type ```chmod o-w project_k.txt```, where ```chmod``` is the command to change directory/file permissions. Next, ```o``` indicates I am changing the permission for the others group followed by  ```-w``` to indicate I am removing their write permission. Lastly ```project_k.txt```is the file on which I am removing their write access.

After removing write access for the others group, I use the command ```ls -l``` once again to show all the files in projects, as well as full details, which include the updated user permissions. Now, the others group no longer has write access for ```project_k.txt```, which can be seen in the image below.

![Changing the file permissions of the others group](https://i.imgur.com/vRYArcm.png)

### Change file permissions on a hidden file

Recently a hidden file was archived titled ```.project_x.txt```. My organization wants the file to have no write permissions for anyone, however, the user and group will still be able to read it. We will be modifying the permissions for ```.project_x.txt```. We can identify ```.project_x.txt``` as a hidden file because it starts with a “```.```” character.

In order to edit these file permissions on the hidden file, I used the ```chmod``` command to remove the write access of the user, which can be done with ```u-w```. I then used ```g-w``` to remove the write access for the group. Next, I used ```g+r``` to give read access to the group, which it did not have before. Lastly, I used ```ls -la``` to confirm the new permissions for the file.

The following code demonstrates how I did that:
![Screenshot showcasing what a hidden file on Linux looks like](https://i.imgur.com/omUuFYz.png)

### Change directory permissions

My organization would like ```researcher2```, and only ```researcher2```, to be allowed access to the ```drafts``` directory and its contents. In order to do this, I will need to edit the execute (```x```) permissions. In the command line, I used ```chmod``` to edit ```drafts``` by using ```g-x```. This removed access for group. Now, using ```ls -l```, the directory permissions have been updated and only the user (```researcher2```) has access to the ```drafts``` folder.

The following code demonstrates how I did that:
![Updating permissions to a directory](https://i.imgur.com/arJApaY.png)

### Summary

I used various Linux commands to check, edit, and confirm different permission levels for directories and files in ```projects```. Using ```chmod``` I was able to edit the permission levels. Lastly, using ```ls -la``` I was able to see a list of the updated permissions for every file.




