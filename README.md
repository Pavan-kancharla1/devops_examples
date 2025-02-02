
# CONNECTING WITH AWS CLI FROM MY MACHINE & LAUNCHING NEW EC2 INSTANCE
# A. Install or update the AWS CLI
To update your current installation of AWS CLI on Windows, download a new installer each time you update to overwrite previous versions. AWS CLI is updated regularly. To see when the latest version was released, see the AWS CLI version 2 Changelog on GitHub.

   # 1.	Download and run the AWS CLI MSI installer for Windows (64-bit):
    https://awscli.amazonaws.com/AWSCLIV2.msi
Alternatively, you can run the msiexec command to run the MSI installer.
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi
For various parameters that can be used with msiexec, see msiexec on the Microsoft Docs website. For example, you can use the /qn flag for a silent installation.
C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi /qn

   # 2.	check aws installation & aws version
	To confirm the installation, open the Start menu, search for cmd to open a command prompt window, and at the command prompt use the aws --version command.
	C:\> aws --version
aws-cli/2.19.1 Python/3.11.6 Windows/10 exe/AMD64 prompt/off
If Windows is unable to find the program, you might need to close and reopen the command prompt window to refresh the path, or follow the troubleshooting in Troubleshooting errors for the AWS CLI.
# B. Configure AWS account
	It's always recommended to create IAM user then login
	AWS console > account > security credentials > create access keys > copy Access key& secret access key
   windows > cmd >
      $ aws configure
      $ paste access keys
   ---> now you are able to connected to aws account
     you can test using any aws cli commamd

# C. Launch new EC2 instance
	Go to AWS CLI documentation & get the required data to launch new EC2 instance
 $ aws ec2 run-instances --image-id ami-xxxxxxxx --count 1 --instance-type t2.micro --key-name MyKeyPair --security-group-ids sg-903004f8 --subnet-id subnet-6e7f829e
 	
  	AMI-ID : Ubuntu 24:04 ami-04b4f1a9cf54c11d0
  	Instance type: t2.micro
   	vpc: vpc-049d7bb2e029dc1af
    	Key pair: create new key pair using cli
     			$ aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem
				Explanation:--key-name MyKeyPair → Specifies the name of the key pair. Change MyKeyPair as needed.
    					--query 'KeyMaterial' --output text > MyKeyPair.pem → Saves the private key to a .pem file.
	Security-group-ID:
 	subnet-ID:
  # or to run with default configuration 
  # $ aws ec2 run-instances --image-id ami-xxxxxxxxxxxxxxxxx --instance-type t2.micro --region us-east-1
  Ex: aws ec2 run-instances --image-id ami-04b4f1a9cf54c11d0 --instance-type t2.micro --key-name ec2key --region us-east-1
  Note: make sure you are connecting instance from the folder where private key available

#  Congratulations you have succesfully launched an EC2 instance.
  

    	
  	


   
