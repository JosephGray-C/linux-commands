# linux-commands

- Adding a user to group
    - sudo usermod -aG thegroupname username

- Print the current working directory
    - pwd

-  Use man command to know what another commnad does
    - man touch
    - man echo
    - man sudo

- This command shows the hidding files
    - ls -a 

- This command shows the permissions of each file or folder
    - ls -l

- This command shows the permissions of the current folder
    - ls -ld

- This commands show u the groups your user is part of
    - getent group odoo
    - groups
    - groups username

- Set group ownership of a folder
    - sudo chown -R username:username /path/to/the/folder

- Permissions to a folder or path
    - sudo chmod -R 775 /path/to/the/folder
    - 1 is execute
    - 2 is writting
    - 4 is reading

- 
