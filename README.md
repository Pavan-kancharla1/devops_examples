# devops_examples
Here is my DevOps hands-on projects for learning
# CONNECTING WITH AWS CLI FROM MY MACHINE
# Install or update the AWS CLI
To update your current installation of AWS CLI on Windows, download a new installer each time you update to overwrite previous versions. AWS CLI is updated regularly. To see when the latest version was released, see the AWS CLI version 2 Changelog on GitHub.
# 1.	Download and run the AWS CLI MSI installer for Windows (64-bit):
    https://awscli.amazonaws.com/AWSCLIV2.msi
Alternatively, you can run the msiexec command to run the MSI installer.
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
For various parameters that can be used with msiexec, see msiexec on the Microsoft Docs website. For example, you can use the /qn flag for a silent installation.
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi /qn
# 2.	To confirm the installation, open the Start menu, search for cmd to open a command prompt window, and at the command prompt use the aws --version command.
	C:\> aws --version
aws-cli/2.19.1 Python/3.11.6 Windows/10 exe/AMD64 prompt/off
If Windows is unable to find the program, you might need to close and reopen the command prompt window to refresh the path, or follow the troubleshooting in Troubleshooting errors for the AWS CLI.

