# Simple Use of the Linux Terminal

## Backend Overview

The backend of a web application refers to the server-side components that handle data processing, storage, and communication with the client-side. Understanding how to navigate and manage files on a server using the Linux terminal is essential for backend development.

## Why Know Terminal Commands

Knowing terminal commands is crucial for developers as it allows for efficient file management, system navigation, and automation of tasks. The terminal provides a powerful interface for interacting with the operating system, especially in server environments where graphical interfaces may not be available.

## The Basics: `ls`, `pwd`

- **`ls`**: Lists the files and directories in the current directory. You can use flags like `-l` for detailed information or `-a` to show hidden files.

    ```bash
    ls -l  # Lists files with detailed information
    ```

- **`pwd`**: Prints the current working directory, showing the full path of the directory you are currently in.

    ```bash
    pwd  # Outputs the current directory path
    ```

## Changing Directories

The `cd` command is used to change the current directory. You can navigate to a specific directory by providing its path.

```bash
cd /path/to/directory  # Changes to the specified directory
cd ..                  # Moves up one directory level
cd ~                   # Changes to the home directory
```

## Relative vs Absolute Paths

- **Absolute Path**: A complete path from the root directory to the target file or directory. It always starts with a `/`.

    ```bash
    /home/user/documents/file.txt  # Absolute path example
    ```

- **Relative Path**: A path relative to the current directory. It does not start with a `/`.

    ```bash
    documents/file.txt  # Relative path example (from the current directory)
    ```

## Making Directories

The `mkdir` command is used to create new directories.

```bash
mkdir new_directory  # Creates a new directory named "new_directory"
```

## Manpages and Flags

- **Manpages**: The `man` command displays the manual pages for other commands, providing detailed information about their usage, options, and flags.

    ```bash
    man ls  # Displays the manual for the ls command
    ```

- **Flags**: Options that modify the behavior of commands. For example, `-r` for recursive operations or `-f` for forceful actions.

## Touch Command

The `touch` command is used to create an empty file or update the timestamp of an existing file.

```bash
touch newfile.txt  # Creates a new empty file named "newfile.txt"
```

## Removing Files and Folders

- **Removing Files**: The `rm` command is used to delete files. Use the `-f` flag to force deletion without prompts.

    ```bash
    rm file.txt  # Removes the specified file
    rm -f file.txt  # Forcefully removes the file without confirmation
    ```

- **Removing Directories**: The `rmdir` command removes empty directories, while `rm -r` removes directories and their contents recursively.

    ```bash
    rmdir empty_directory  # Removes an empty directory
    rm -r directory_name  # Removes a directory and all its contents
    ```
