- ## Storage, Files Systems, Files
    - ### [Partitioning]
    - ### [File Systems]
    - ### [Algorithms]
    - ### [Data Structures]
- ## Processes
    - ### [Samples]
    - ### Java
    - ### [Android Studio]
    - ### Gradle
    - ### Google Services
- ## Users
- ## Shell

<br><br><br><br>

## Partitioning
- Partitioning utility
```bash
fdisk /dev/sdb
```
```bash
mkswap device_file
swapon device_file
swapoff [device_file]
```
## File Systems
- **ls** *file* - show information about file or folder
- **cp** [options] *source destination*
    - Eg.: **cp file1 file2**; **cp -r dir1 dir2**
- **mv** *source destination*

## Shell
- ## Reverse search
    - Say you want to find a command you typed earlier, that starts with ssh. 
    - Press **Ctrl+R** and type ssh. **Ctrl+R** will start search from most recent command to old one (reverse-search). If you have more than one command which starts with ssh, Press Ctrl+R again and again until you find the match.
    - Once you've found the match you can press Enter to execute the command or left / right cursor to just select the text of the command.
    - If you just want to search your history, you can just use history | grep ssh, substituting ssh for whatever you want to search.