# FileClear
I tested this using Ubuntu 20.04.
The program is written in C# and requires the dotnet 3.1 runtime environment in order to work. If you guys don’t have it on your systems this link has instructions for installing it, just replace the 5.0 with 3.1:
https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu#2004-
There are 4 files in this repository:
• FileClear.1.0.0.deb - The Debian package of my program. Can be installed once the dotnet
runtime environment is there. When you run it it should get installed to /usr/share/FileClear.
• FileClear.service - To be placed in /etc/systemd/system/ Once in there you should be able to
start the service using systemctl start FileClear. Or you can just set it to start at boot by enabling
it. If the program runs into an issue and quits it will restart after 5 seconds.
• test.txt - This is a configuration file that the service checks when it starts to load in the disc
usage it needs to check for, and what folders it is to clear if the usage threshold is reached. The file is in the format of the the first line being the usage percentage and the following lines being the folders to be cleared, a new line for each folder. The test file has the usage set at 50 percent, and checks one folder at /home/testclear.
• The program expects this file to be at /home/test.txt. If it is not there or changes are made to the file you will need to reload the service for the changes to reflect in the running program.
• FileClear.zip - A zip file of the original program. The code is all in Program.cs.
