# linux-commands
- command options(flags) arguments

- pwd

- mkdir

- touch

- rm

- rmdir

- ls

- mv

- cp

- cd

- history

- type

- man

- grep

- FLAGS = each letter after the "-" is an option
    - ls -la
    - cp -p
    - cp -pr
    - mkdir -p
    - rm -rfv

- chmod
    - chmod u+x archivo.sh      # añade permiso de ejecución al usuario
    - chmod g-w archivo.txt     # quita permiso de escritura al grupo
    - chmod o=r archivo.txt     # solo lectura para otros
    - chmod u=rwx,g=rx,o=r archivo.txt
    - chmod 755 script.sh       # usuario rwx (7), grupo r-x (5), otros r-x (5)

- chgrp
    - chgrp estudiantes ./script.sh

- chown
    - chown joseph ./script.sh
    - chown -r user:group /folder # cambia usuario y grupo recursivamente

- r = 4
- w = 2
- x = 1

- USER MANAGEMENT COMMANDS
    - useradd
        - sudo useradd jose
    - usermod
        | Option | Description                     | Example                           |
        | ------ | ------------------------------- | --------------------------------- |
        | `-l`   | Change login name               | `sudo usermod -l newname oldname` |
        | `-d`   | Change home directory           | `sudo usermod -d /home/new jose`  |
        | `-s`   | Change login shell              | `sudo usermod -s /bin/zsh jose`   |
        | `-aG`  | Add to secondary group (append) | `sudo usermod -aG sudo jose`      |
        | `-L`   | Lock account (disable login)    | `sudo usermod -L jose`            |
        | `-U`   | Unlock account                  | `sudo usermod -U jose`            |
        - sudo usermod -aG sudo jose
            - sudo usermod -aG groupname username
            - sudo usermod -aG sudo jose
            - sudo usermod -aG sudo,developers,network username
            - If you omit -a, like this:
                - sudo usermod -G sudo jose
                - Then jose will be removed from all other groups and left only in sudo — which can break access permissions.
            | Option   | Meaning    | Explanation                                                                           |
            | -------- | ---------- | ------------------------------------------------------------------------------------- |
            | **`-a`** | **append** | Adds the user to the group(s) **without removing them** from existing ones.           |
            | **`-G`** | **groups** | Specifies one or more **secondary (supplementary) groups** the user should belong to. |
    - userdel
        - sudo userdel -r jose
    - passwd
        - sudo passwd jose
    - id
        - id username
    - whoami
    - chage
        - chage = change password age policy
        - It helps control how often and when a user must change their password.
        - sudo chage -M 90 username
        | Option    | Meaning                                                   | Example                         |
        | --------- | --------------------------------------------------------- | ------------------------------- |
        | `-l`      | List current password aging info for the user             | `sudo chage -l jose`            |
        | `-M DAYS` | Set **maximum** days password is valid                    | `sudo chage -M 90 jose`         |
        | `-m DAYS` | Set **minimum** days before password can be changed again | `sudo chage -m 7 jose`          |
        | `-W DAYS` | Warn user DAYS before password expires                    | `sudo chage -W 10 jose`         |
        | `-E DATE` | Set **account expiration date** (YYYY-MM-DD)              | `sudo chage -E 2025-12-31 jose` |
        | `-I DAYS` | Disable account if password is expired for DAYS           | `sudo chage -I 5 jose`          |

- GROUP MANAGEMENT COMMANDS
    | Command        | Meaning        | What it does                                        | Example                            |
    | -------------- | -------------- | --------------------------------------------------- | ---------------------------------- |
    | **`groupadd`** | Add group      | Creates a new group.                                | `sudo groupadd developers`         |
    | **`groupdel`** | Delete group   | Deletes a group.                                    | `sudo groupdel developers`         |
    | **`groupmod`** | Modify group   | Changes group name or GID.                          | `sudo groupmod -n devs developers` |
    | **`gpasswd`**  | Group password | Sets or manages group administrators and passwords. | `sudo gpasswd developers`          |
    - groupadd
    - groupdel
    - groupmod
    - gpasswd
    - groups
    - groups username

----------OLD NOTES----------

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
