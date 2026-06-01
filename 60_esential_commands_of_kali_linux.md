========================================================================
             KALI LINUX ESSENTIAL COMMANDS CHEAT SHEET
========================================================================
This reference guide categorizes and details the essential commands 
required for system navigation, administration, and network operations 
in Kali Linux.
========================================================================

Before diving deep into advanced tools, mastering these foundational 
commands is essential. All standard Linux commands can be organized 
into the following six core categories:

1.) Filesystem Navigation Commands: Used to traverse files and directories.[cite: 1]
2.) File and Directory Commands: Used to manipulate, create, edit, and delete files/folders.
3.) User and Permission Commands: Used to control system access and ownership.
4.) Process and System Monitoring Commands: Used to track, manage, and monitor active system processes.
5.) System Operation Commands: Used to perform operations at the core system level.
6.) Network Commands: Critical utilities for interacting with network interfaces and internet protocols.

------------------------------------------------------------------------
                         QUICK REFERENCE LIST
------------------------------------------------------------------------

1.) FILESYSTEM NAVIGATION COMMANDS[cite: 1]
pwd         Show current directory path
cd          Change directory
locate      Search files by name
find        Search files and directories

2.) FILE AND DIRECTORY COMMANDS
mkdir       Create a directory
rmdir       Remove an empty directory
rm          Delete files or directories
cp          Copy files or directories
mv          Move or rename files
touch       Create an empty file
file        Show file type
zip         Compress files into ZIP archive
unzip       Extract ZIP archive
tar         Archive files and directories
nano        Edit files with Nano
vi          Edit files with Vi
jed         Edit files with Jed
cat         Display file content
grep        Search text patterns in files
sed         Replace or modify text patterns
head        Show first lines of a file
tail        Show last lines of a file
awk         Process and analyze text
sort        Sort file content
cut         Extract sections of text
diff        Compare two files
tee         Output to terminal and file

3.) USER AND PERMISSION COMMANDS
sudo        Run command as administrator
su          Switch user account
whoami      Show current user
chmod       Change file permissions
chown       Change file ownership
useradd     Create new user
userdel     Delete user account
passwd      Set or change password

4.) PROCESS AND SYSTEM MONITORING COMMANDS
df          Show disk space usage
du          Show directory size
top         Display running processes
htop        Interactive process viewer
ps          Show process snapshot
uname       Show system information
hostname    Show or set hostname
time        Measure command execution time
systemctl   Manage system services
watch       Run command repeatedly
jobs        List shell background jobs
kill        Terminate a process
shutdown    Shut down or restart system

5.) SYSTEM OPERATION COMMANDS
history     Show command history
man         Show command manual
echo        Print text to terminal
ln          Create file links
alias       Create command shortcut
unalias     Remove command shortcut
cal         Display calendar
apt         Manage packages (Debian-based)
dnf         Manage packages (RHEL-based)

6.) NETWORK COMMANDS (MOST IMPORTANT)
ping        Test network connectivity
wget        Download files from the web
curl        Transfer data via URL
scp         Copy files over SSH
rsync       Sync files between systems
ip          Manage network settings
netstat     Show network connections
traceroute  Trace network packet path
nslookup    Query DNS records
dig         Detailed DNS lookup

------------------------------------------------------------------------
                        SYNTAX AND WAY OF USES
------------------------------------------------------------------------

1. ls command
The ls command displays files and directories within a specified location.
Syntax:
ls [options] [directory_or_path]
Common options:
• -a → shows hidden files, including those starting with a dot (.)
• -l → displays a detailed list with permissions, ownership, size, and timestamps
Example:
ls -Ra /path/to/dir
Lists all files and subdirectories recursively inside /path/to/dir, including hidden files, allowing you to inspect the full directory structure.

2. pwd command
The pwd command prints the full path of the current working directory.
Syntax:
pwd [options]
Common options:
• -L → prints the logical path using symbolic links or environment shortcuts
• -P → prints the physical path by resolving all symbolic links
Example:
pwd -P
Displays the exact directory path without symbolic links, helping verify the actual location of the current working directory.

3. cd command
The cd command changes the current working directory to a specified location.
Syntax:
cd [path_or_directory]
Common shortcuts:
• cd   → moves to the current user’s home directory
• cd .. → moves one directory up
• cd -  → returns to the previous directory
Example:
cd /var/www/html
Changes the current directory to /var/www/html, allowing you to access and manage files in that location.

4. mkdir command
The mkdir command creates one or more directories at a specified location.
Syntax:
mkdir [options] directory_name1 directory_name2
Common options:
• -m → sets custom permissions for the new directory (e.g., -m 755)
• -p → creates parent directories as needed and avoids errors if they already exist
Example:
mkdir -p /path/to/target_folder/new_folder
Creates the directory /path/to/target_folder/new_folder, including any missing parent directories, allowing you to build nested folder structures in one command.

5. rmdir command
The rmdir command removes empty directories from the file system.
Syntax:
rmdir [options] directory_name
Common options:
• -p → removes parent directories if they also become empty after the deletion
Example:
rmdir /path/to/empty_folder
Removes the specified empty directory, helping keep the file system tidy without risking data loss.

6. rm command
The rm command removes files or directories from the file system.
Syntax:
rm [options] file1 file2
Common options:
• -r → removes directories and their contents recursively
• -f → forces deletion without confirmation prompts
• -i → prompts for confirmation before each removal
Example:
rm -rf folder-name
Deletes the directory folder-name and all its contents recursively without confirmation, which is useful for cleanup tasks but requires caution to avoid accidental data loss.

7. cp command
The cp command copies files or directories from one location to another.
Syntax:
cp [options] source_file target_path
Common options:
• -R → copies directories and their contents recursively
• -i → prompts before overwriting existing files
• -v → displays detailed output of the copy process
Example:
cp -R /path/to/folder /target/path/to/folder_copy
Copies the directory /path/to/folder and all its contents to /target/path/to/folder_copy, preserving the structure for backup or duplication tasks.

8. mv command
The mv command moves or renames files and directories.
Syntax:
mv [options] source target
Common options:
• -i → prompts before overwriting existing files
• -v → displays detailed output of the move operation
• -n → prevents overwriting existing files
Example:
mv /original/path/file1.txt /new/file/directory/
Moves file1.txt from /original/path/ to /new/file/directory/, allowing you to reorganize files or relocate them to a different folder.

9. touch command
The touch command creates a new empty file or updates the timestamp of an existing file.
Syntax:
touch [options] [path_and_file_name]
Common options:
• -c → avoids creating a file if it does not exist
• -t → sets a specific timestamp for the file
• -a → updates only the access time
Example:
touch file.txt
Creates an empty file named file.txt in the current directory, allowing you to quickly generate placeholder or configuration files.

10. file command
The file command identifies the type of a file based on its content.
Syntax:
file [file_name]
Common options:
• -k → displays additional information about the file type
• -i → shows the MIME type of the file
• -L → follows symbolic links and reports the actual file type
Example:
file hostinger_sym.txt
Displays the actual file type that hostinger_sym.txt points to, which helps verify symbolic links or detect unknown file formats.

11. zip and unzip commands
The zip command compresses files or directories into a ZIP archive, while the unzip command extracts files from a ZIP archive.
Syntax:
zip [options] zip_file_name file1 file2
unzip [options] zip_file_name
Common options:
• -r (zip) → compresses directories recursively
• -e (zip) → encrypts the archive with a password
• -l (unzip) → lists contents of the archive without extracting
• -d (unzip) → extracts files to a specified directory
Example:
zip -r archive.zip /path/to/folder && unzip archive.zip
Creates a compressed archive archive.zip from /path/to/folder and then extracts its contents into the current directory, allowing you to bundle and restore files efficiently.

12. tar command
The tar command creates, extracts, and manages archive files that bundle multiple files or directories.
Syntax:
tar [options] tar_file_name file1 file2
Common options:
• -c → creates a new archive
• -x → extracts files from an archive
• -f → specifies the archive file name
• -z → compresses or decompresses using gzip
Example:
tar -czf archive.tar.gz file1.txt file2.txt
Creates a compressed archive archive.tar.gz containing file1.txt and file2.txt, allowing you to bundle and reduce file size in a single command.

13. nano, vi, and jed commands
The nano, vi, and jed commands open and edit text files directly in the terminal.
Syntax:
nano file_name
vi file_name
jed file_name
Example:
nano file.txt
Opens file.txt in the Nano text editor, allowing you to create or modify file content directly from the terminal.

14. cat command
The cat command displays, combines, or creates files by reading and writing file content.
Syntax:
cat [options] file_name
Common options:
• -n → displays line numbers alongside file content
• -b → displays line numbers for non-empty lines only
• -s → suppresses repeated empty lines
Example:
cat file1.txt file2.txt > target.txt
Combines the contents of file1.txt and file2.txt into target.txt, allowing you to merge multiple files into a single output file.

15. grep command
The grep command searches for specific patterns or keywords within files or command output.
Syntax:
grep [options] keyword [file]
Common options:
• -i → performs a case-insensitive search
• -r → searches recursively through directories
• -n → displays line numbers with matching results
Example:
ls | grep "file.txt"
Filters the output of the ls command to show only entries that match file.txt, allowing you to quickly locate specific items in a list.

16. sed command
The sed command searches, replaces, and transforms text within files or input streams.
Syntax:
sed [options] 's/pattern/replacement/' file
Common options:
• -i → edits files in place without creating a new output
• -n → suppresses automatic output (used with explicit print commands)
• -e → allows multiple editing expressions
Example:
sed 's/red/blue/' colors.txt
Replaces the first occurrence of red with blue in each line of colors.txt, allowing quick text modifications without opening a file manually.

17. head command
The head command displays the first lines or bytes of a file or command output.
Syntax:
head [options] file_name
Common options:
• -n → specifies the number of lines to display
• -c → specifies the number of bytes to display
Example:
head -n 5 file.txt
Displays the first five lines of file.txt, allowing you to quickly preview the beginning of a file without opening it fully.

18. tail command
The tail command displays the last lines or bytes of a file or command output.
Syntax:
tail [options] file_name
Common options:
• -n → specifies the number of lines to display
• -c → specifies the number of bytes to display
• -f → follows the file in real time as new lines are added
Example:
ping -c 10 8.8.8.8 | tail -n 5
Displays the last five lines of the ping command output, allowing you to focus on the most recent results or summaries.

19. awk command
The awk command processes and analyzes text by applying patterns and actions to structured data.
Syntax:
awk 'pattern {action}' input_file
Common options:
• -F → specifies a custom field separator
• -v → assigns variables for use within the command
• -f → reads the awk program from a file
Example:
awk -F':' '{ total += $2; students[$1] = $2 } END { average = total / length(students); for (student in students) if (students[student] > average) print student }' score.txt
Calculates the average value from score.txt and prints the names of entries with values above the average, allowing you to perform data analysis directly in the terminal.

20. sort command
The sort command arranges lines of text in a file or input stream in a specified order.
Syntax:
sort [options] [file_name]
Common options:
• -r → sorts in reverse order
• -n → sorts numerically instead of alphabetically
• -k → sorts based on a specific column or field
Example:
sort -n file.txt
Sorts the contents of file.txt numerically and prints the result to the terminal without modifying the original file.

21. cut command
The cut command extracts specific sections of text from each line of a file or input stream.
Syntax:
cut [options] file
Common options:
• -f → selects specific fields (columns)
• -d → specifies a delimiter to separate fields
• -c → extracts specific character positions
• -b → extracts specific byte ranges
Example:
cut -d',' -f3-5 list.txt
Extracts the third to fifth fields from each line in list.txt using a comma as the delimiter, allowing you to isolate structured data from files like CSVs.

22. diff command
The diff command compares two files and displays the differences between them.
Syntax:
diff [options] file_name1 file_name2
Common options:
• -c → displays differences in context format with surrounding lines
• -u → shows unified output format (commonly used for patches)
• -i → ignores differences in letter case
Example:
diff -c 1.txt 2.txt
Displays the differences between 1.txt and 2.txt with surrounding context, making it easier to understand changes between file versions.

23. tee command
The tee command writes command output to both the terminal and a file simultaneously.
Syntax:
command | tee [options] file_name
Common options:
• -a → appends output to the file instead of overwriting it
• -i → ignores interrupt signals (useful in pipelines)
Example:
ping 8.8.8.8 | tee -a test_network.txt
Appends the output of the ping command to test_network.txt while displaying it in the terminal, allowing you to monitor and save results at the same time.

24. locate command
The locate command searches for files by name using a prebuilt system database.
Syntax:
locate [options] keyword
Common options:
• -i → performs a case-insensitive search
• -r → searches using a regular expression
• -n → limits the number of results displayed
Example:
locate -i filename.txt
Searches for all files matching filename.txt regardless of case, returning results quickly based on the system’s file index.

25. find command
The find command searches for files and directories in a specified path based on conditions.
Syntax:
find [path] [options] expression
Common options:
• -name → searches for items by name
• -type f → limits results to files
• -type d → limits results to directories
Example:
find /path/to/folder -type f -name "file.txt"
Searches for a file named file.txt within /path/to/folder, returning matches in real time based on the specified criteria.

26. sudo command
The sudo command runs a command with elevated (administrator) privileges.
Syntax:
sudo [options] command
Common options:
• -u → runs the command as a specified user
• -i → starts a shell with root privileges
• -l → lists allowed commands for the current user
Example:
sudo nano file.txt
Opens file.txt in the Nano editor with administrator privileges, allowing you to modify system-level files that require elevated access.

27. su and whoami commands
The su command switches the current user to another user account, while the whoami command displays the currently logged-in user.
Syntax:
su [options] [username]
whoami
Common options:
• -   → starts a login shell for the target user
• -c  → runs a single command as the specified user
Example:
su - root
Switches to the root user and starts a login shell, allowing you to execute commands with full system privileges.

28. chmod command
The chmod command changes file and directory permissions for users, groups, and others.
Syntax:
chmod [options] permissions file_or_directory
Common options:
• -R → applies changes recursively to directories and their contents
• -v → displays a message for each processed file
• -c → reports only when a change is made
Example:
chmod 744 file1.txt
Sets permissions for file1.txt so the owner can read, write, and execute, while others can only read, allowing controlled access to the file.

29. chown command
The chown command changes the ownership of files and directories.
Syntax:
chown [options] owner:group file1 file2
Common options:
• -R → applies ownership changes recursively
• -v → displays a message for each processed file
• -c → reports only when a change is made
Example:
chown admin-vps:developers file1.txt
Sets admin-vps as the owner and developers as the group for file1.txt, allowing proper access control and file management.

30. useradd, passwd, and userdel commands
The useradd command creates a new user account, the passwd command sets or updates a user’s password, and the userdel command removes a user account.
Syntax:
useradd [options] username
passwd username
userdel [options] username
Common options:
• -m (useradd) → creates a home directory for the user
• -r (userdel) → removes the user’s home directory and files
• -l (passwd)  → locks a user account
Example:
sudo useradd -m newuser && sudo passwd newuser
Creates a new user newuser with a home directory and sets a password, allowing the account to log in and use the system.

31. df command
The df command displays disk space usage for file systems.
Syntax:
df [options] [file_system]
Common options:
• -h → shows output in human-readable format (KB, MB, GB)
• -T → displays the file system type
• -a → includes all file systems, including empty ones
Example:
df -h
Displays disk usage for all mounted file systems in a human-readable format, helping you quickly assess available and used storage space.

32. du command
The du command checks the size of a directory and its content.
Syntax:
du [directory]
Notes:
• The command will check your working directory if you don’t specify a path or folder.
• By default, it breaks down each subfolder’s disk usage, but you can add the -s option to summarize the total usage in one output.
• You can also use the -M option to change the information from KB to MB.

33. top command
The top command displays real-time information about running processes and system resource usage.
Syntax:
top [options]
Common options:
• -p → monitors a specific process by its ID (PID)
• -d → sets the delay between screen updates
• -u → shows processes for a specific user
Example:
top -u root
Displays real-time resource usage for processes owned by the root user, helping you monitor system performance and identify resource-heavy tasks.

34. htop command
The htop command displays and manages running processes in an interactive interface.
Syntax:
htop [options]
Common options:
• -d     → sets the update interval
• -u     → shows processes for a specific user
• --tree → displays processes in a hierarchical tree view
Example:
htop
Opens an interactive process viewer that shows CPU and memory usage, allowing you to navigate, filter, and manage processes in real time.

35. ps command
The ps command displays a snapshot of currently running processes.
Syntax:
ps [options]
Common options:
• -A → shows all running processes
• -u → displays processes for a specific user
• -r → lists only running processes
Example:
ps -A
Displays all active processes on the system at a specific moment, allowing you to inspect process IDs, statuses, and resource usage.

36. uname command
The uname command displays system information such as the kernel, architecture, and operating system.
Syntax:
uname [options]
Common options:
• -a → displays all available system information
• -r → shows the kernel release version
• -m → displays the machine hardware architecture
Example:
uname -a
Displays complete system information, including kernel version and architecture, helping you identify your Linux environment.

37. hostname command
The hostname command displays or sets the system’s hostname.
Syntax:
hostname [options]
Common options:
• -i → displays the IP address of the host
• -a → shows the hostname alias
• -A → displays the fully qualified domain name (FQDN)
Example:
hostname -A
Displays the system’s fully qualified domain name, helping identify the server within a network or domain.

38. time command
The time command measures how long a command or script takes to execute.
Syntax:
time command
Example:
time ls -la
Measures how long the ls -la command takes to run, providing execution time details such as real, user, and system time.

39. systemctl command
The systemctl command manages services in your Linux system.
Syntax:
systemctl subcommand [service_name] [options]
Notes:
• The subcommands represent your task, like listing, restarting, terminating, or enabling services.
• Example to list all unit files:
  sudo systemctl list-unit-files --type service --all
• Note that this command might not work with older distributions using alternative service managers.

40. watch command
The watch command runs a command repeatedly at specified intervals and displays the updated output.
Syntax:
watch [options] command
Common options:
• -n → sets the interval in seconds between executions
• -d → highlights changes between updates
Example:
watch -n 5 netstat
Runs the netstat command every five seconds and updates the output, allowing you to monitor changes in network activity over time.

41. jobs command
The jobs command lists background and suspended jobs in the current shell session.
Syntax:
jobs [options] [job_id]
Common options:
• -l → displays job IDs along with process IDs
• -n → shows only jobs that have changed status
• -p → lists only process IDs
Example:
jobs -l
Displays all jobs in the current shell with their process IDs, allowing you to monitor and manage background tasks.

42. kill command
The kill command sends a signal to terminate or control a process by its process ID (PID).
Syntax:
kill [signal] process_id
Common options:
• -15 → sends the default SIGTERM signal for graceful termination
• -9  → sends SIGKILL to forcefully terminate a process
• -l  → lists all available signals
Example:
kill -9 1234
Forcefully terminates the process with ID 1234, which is useful when a program becomes unresponsive.

43. shutdown command
The shutdown command powers off or restarts the system at a specified time.
Syntax:
shutdown [options] [time] [message]
Common options:
• -r → restarts the system instead of shutting it down
• -h → halts or powers off the system
• -c → cancels a scheduled shutdown
Example:
shutdown -r +5
Schedules a system restart in five minutes, allowing users to prepare before the system goes offline.

44. ping command
The ping command sends network packets to a target host and measures the response time.
Syntax:
ping [options] [hostname_or_ip]
Common options:
• -c → specifies the number of packets to send
• -i → sets the interval between packets
• -s → defines the packet size
Example:
ping -c 15 -i 2 google.com
Sends 15 packets to google.com at two-second intervals, allowing you to test connectivity and measure network latency.

45. wget command
The wget command downloads files from the internet using HTTP, HTTPS, or FTP protocols.
Syntax:
wget [options] [url]
Common options:
• -O → saves the file with a custom name
• -c → resumes a partially downloaded file
• -q → runs in quiet mode without output
Example:
wget https://wordpress.org/latest.zip
Downloads the file from the specified URL to the current directory, allowing you to retrieve remote resources directly from the terminal.

46. cURL command
The curl command transfers data to or from a server using a specified URL.
Syntax:
curl [options] url
Common options:
• -O → downloads a file and saves it with its original name
• -o → saves the file with a custom name
• -X → specifies the HTTP method (GET, POST, PUT, DELETE)
Example:
curl -X GET https://api.example.com/endpoint
Sends a GET request to the specified API endpoint and returns the response, allowing you to test APIs or retrieve remote data directly from the terminal.

47. scp command
The scp command securely copies files and directories between local and remote systems over SSH.
Syntax:
scp [options] source destination
Common options:
• -P → specifies a custom SSH port
• -r → copies directories recursively
• -C → enables compression during transfer
Example:
scp file1.txt root@185.185.185.185:/path/to/folder
Copies file1.txt from the local machine to the remote server at /path/to/folder, allowing secure file transfer between systems.

48. rsync command
The rsync command synchronizes files and directories between locations while minimizing data transfer.
Syntax:
rsync [options] source destination
Common options:
• -a → preserves file attributes (permissions, timestamps, symbolic links)
• -z → compresses data during transfer
• -v → displays detailed transfer output
Example:
rsync -avz /path/to/local/folder/ vps-user@185.185.185.185:/path/to/remote/folder/
Synchronizes the local folder with the remote directory while preserving attributes and compressing data, resulting in faster, more efficient transfers.

49. ip command
The ip command displays and manages network interfaces, addresses, and routing.
Syntax:
ip [options] object command
Common keywords:
• address → manages and displays IP addresses
• link    → manages network interfaces
• route   → displays or modifies routing tables
Example:
ip address show
Displays all network interfaces and their assigned IP addresses, helping you inspect and troubleshoot network configuration.

50. netstat command
The netstat command displays network connections, routing tables, and interface statistics.
Syntax:
netstat [options]
Common options:
• -a → shows all connections, including listening sockets
• -t → displays TCP connections
• -u → displays UDP connections
• -r → shows routing tables
Example:
netstat -tuln
Displays all listening TCP and UDP ports, helping you identify active network services and open ports.

51. traceroute command
The traceroute command tracks the path packets take to reach a destination host.
Syntax:
traceroute [options] destination
Common options:
• -m → sets the maximum number of hops
• -n → disables DNS resolution for faster output
• -w → sets the timeout in seconds for each response
Example:
traceroute google.com
Displays each hop between your system and google.com, helping you identify network delays or routing issues.

52. nslookup command
The nslookup command queries DNS servers to retrieve domain or IP address information.
Syntax:
nslookup [options] domain_or_ip [dns_server]
Common options:
• -type=  → specifies the DNS record type (e.g., A, MX, TXT)
• -retry= → sets the number of query retries
• -port=  → uses a specific DNS server port
Example:
nslookup -type=MX example.com
Retrieves the mail exchange (MX) records for example.com, helping you inspect DNS configuration and troubleshoot domain-related issues.

53. dig command
The dig command queries DNS records and provides detailed information about a domain or IP address.
Syntax:
dig [options] [server] [type] name_or_ip
Common options:
• -x      → performs a reverse DNS lookup
• +short  → displays a concise output
• @server → queries a specific DNS server
Example:
dig MX domain.com
Retrieves the mail exchange (MX) records for domain.com, helping you analyze DNS configuration and troubleshoot domain resolution issues.

54. history command
The history command displays a list of previously executed commands in the current shell session.
Syntax:
history [options]
Common options:
• -c → clears the command history
• -r → reads the history file and appends it to the current session
• -d → deletes a specific entry by its ID
Example:
!145
Re-executes the command with ID 145 from the history list, allowing you to quickly repeat previously used commands.

55. man command
The man command displays the manual page for a specified command.
Syntax:
man [options] [section_number] command_name
Common options:
• -k → searches manuals for keywords
• -f → displays a short description of a a command
• -a → shows all available manual pages for a command
Example:
man 3 ls
Displays the section 3 manual page for ls, allowing you to access detailed documentation for specific command categories.

56. echo command
The echo command outputs text or variables to the terminal or a file.
Syntax:
echo [options] [text]
Common options:
• -n → removes the trailing newline from output
• -e → enables interpretation of escape sequences (\n, \t)
Example:
echo "Hello World" > file.txt
Writes Hello World to file.txt, allowing you to create or overwrite files with custom text output.

57. ln command
The ln command creates links between files, including symbolic (soft) and hard links.
Syntax:
ln [options] source target
Common options:
• -s → creates a symbolic (soft) link
• -f → forces creation by overwriting existing files
• -v → displays detailed output of the operation
Example:
ln -s target.txt shortcut.txt
Creates a symbolic link named shortcut.txt that points to target.txt, allowing you to access the file using an alternative path.

58. alias and unalias commands
The alias command creates a shortcut for a command, while the unalias command removes an existing alias.
Syntax:
alias name='command'
unalias name
Example:
alias k='kill'
Creates an alias k for the kill command, allowing you to run kill using a shorter keyword.

59. cal command
The cal command displays a calendar for a specified month or year.
Syntax:
cal [options] [month] [year]
Common options:
• -3 → displays the previous, current, and next month
• -y → shows the entire year
• -m → displays Monday as the first day of the week
Example:
cal -3
Displays the previous, current, and next month, allowing you to view nearby dates at a glance.

60. apt and dnf commands
The apt command manages packages on Debian-based systems, while the dnf command manages packages on Red Hat-based systems.
Syntax:
apt [options] subcommand
dnf [options] subcommand
Common subcommands:
• install → installs a package
• remove  → removes a package
• update  → updates package lists
• upgrade → upgrades installed packages
Example:
sudo apt install vim
Installs the vim text editor using the APT package manager, allowing you to add new software to the system.
========================================================================