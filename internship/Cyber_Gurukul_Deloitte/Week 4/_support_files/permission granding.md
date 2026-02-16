In Linux, you primarily use the **`chmod`** command to change permissions for the file owner, group, and others. You can use either **symbolic mode** (using letters and symbols) or **numeric mode** (using octal values). 

Prerequisites

- You must be the file's owner or have `sudo`/root privileges to change its permissions.
- You can view current permissions using the `ls -l` command. 

Method 1: Numeric (Absolute) Mode

Numeric mode uses a three-digit number to define permissions for the owner, group, and others, respectively. 

|Permission|Value|
|---|---|
|Read (r)|4|
|Write (w)|2|
|Execute (x)|1|
|No permission (-)|0|

The digits are calculated by summing the values of the desired permissions for each category. 

- **To give the owner read, write, and execute permissions (4+2+1=7), the group read and execute (4+1=5), and others only read (4+0+0=4) for a file named `script.sh`, you would use:**
    
    bash
    
    ```
    chmod 754 script.sh
    ```
    
- **To give the owner read and write permissions, and no permissions to group and others (commonly used for sensitive files like SSH keys), use:**
    
    bash
    
    ```
    chmod 600 filename
    ```
    
     

Method 2: Symbolic Mode

Symbolic mode uses letters to specify whose permissions are being changed and symbols to add (`+`), remove (`-`), or set (`=`) permissions. 

|Who|Symbol|
|---|---|
|User (owner)|`u`|
|Group|`g`|
|Others|`o`|
|All|`a`|

|Operation|Symbol|
|---|---|
|Add permission|`+`|
|Remove permission|`-`|
|Set exact permission|`=`|

- **To add execute permission to the owner (`u`) and group (`g`) for a file named `script.sh`:**
    
    bash
    
    ```
    chmod ug+x script.sh
    ```
    
- **To remove write and execute permissions from others (`o`) for a file named `data.txt`:**
    
    bash
    
    ```
    chmod o-wx data.txt
    ```
    
- **To set the exact permissions for everyone (`a`) to read and write (no execute) for a file named `config.txt`:**
    
    bash
    
    ```
    chmod a=rw config.txt
    ```
    
     

Other Useful Commands

- **Change ownership:** The `chown` command is used to change the user and/or group owner of a file or directory.
    
    bash
    
    ```
    # Change user owner to 'john'
    chown john filename
    # Change user owner to 'john' and group owner to 'dev-team'
    chown john:dev-team filename
    ```
    
- **Change permissions recursively:** The `-R` option applies the permission changes to all files and subdirectories within a given directory.
    
    bash
    
    ```
    chmod -R 755 directory_name
    ```
    
     

_**Warning:**_ Using `chmod 777` on files or directories is generally not recommended as it grants read, write, and execute permissions to _everyone_, posing a significant security risk. 

- [](https://linuxize.com/post/what-does-chmod-777-mean/#:~:text=Setting%20777%20permissions%20\(%20chmod%20777,pose%20a%20huge%20security%20risk.)
    
    What Does chmod 777 Mean - Linuxize
    
