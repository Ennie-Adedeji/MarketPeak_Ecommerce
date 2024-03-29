This README.md file documents  the steps taken to develop an e-commerce website, utilizing Git for version control, developing the platform in a linux environment , and deploying it on an AWS EC2 instance.

The initial step in this project involved comprehending the project's objectives, anticipated outcomes, and outlining the high-level steps needed to achieve them.
## Task 1.1 Initialise git repository
- To achieve this task, firstly, set up Git on your local machine; you can download and install it from the official Git website. Alternatively, you can use a package manager on your operating system to install Git. For example, on Ubuntu, you can install Git using the following command: sudo apt install git.
- This command installs Git on your local machine, next step is to create a directory where you want to initialize the Git repository. You can use the 'mkdir' command to create a new directory; for example "mkdir project-directory".
- Upon creating the directory, navigate into it using the "cd" command. 
- Once you're in the desired directory, run the "git init" command to create a new Git repository. This command generates a .git directory in the current location, containing all the essential files for version control. 
### Task 1.2 Obtain and Prepare the E-commerce Website Template
- This task entails acquiring a pre-designed website template that can be customized to suit our needs and subsequently hosted on a web server. This template will serve as our product, acting as the foundation upon which we'll implement changes and modifications.
- To accomplish this, I visited [Tooplate] (https://www.tooplate.com/) and explored the range of available website templates. After carefully selecting a template that aligned with the project requirements, I proceeded to download it to my local machine.

### Task 1.3 Stage and Commit the template to git
- To accomplish this, firstly, the files were uploaded to a folder named 'MarketPeak_Ecommerce'. Then, the following commands were executed:
- Add template to Git: The "git add ." command was used to stage the template files for commit. This command indicates the inclusion of all content within the current folder into Git, effectively adding the template to version control.
- Setting global configuration with name and email: The command git config --global user.name was utilized to set up my Git username, linking my commits with the corresponding name. This enables other users to pinpoint who made specific changes to the repository. Additionally, the command git config --global user.email was employed to configure my Git email address, serving as an identifier associated with my Git username.
- Making the first commit: After the configuration, the initial commit was executed using the command git commit -m "comment".This  command is used to permanently save the changes to the Git repository. It creates a new commit, which acts as a snapshot of the current state of the project.
- Pushing the changes to Main Repository: To synchronize the local adjustments and configurations with the central repository, the command git push -u origin main was executed. This command uploads the committed changes to the "main" branch on the central repository, ensuring that the central repository reflects the most recent updates made locally.

  ### AWS Deployment
  The process of creating an AWS instance for hosting a website on the server provided by AWS is crucial, because it allows users to leverage the infrastructure and resources offered by AWS to deploy and manage their website. To achieve this for this project, the following steps were considered:
- Firstly i signed in to the AWS Management Console, then navigated to the EC2 dashboard, and clicked  on "Launch Instance" to start the instance creation wizard, i chose an Amazon Machine Image (AMI)- Amazon Linux server. I then selected an instance type based on my workload needs. After that, i configured the instance details such as network settings, storage, tags, and security groups. Additionally , I configured the security groups to permit specific types of inbound traffic. This involved opening ports for HTTP (port 80), HTTPS (port 443), and SSH (port 22). This configuration ensures secure handling of web traffic for the website and enables SSH access for managing the instance via SSH connectivity. After the security inbound roles have to configured, I created a new key pair for SSH access to the instance.Then, I clicked "Launch Instances" to finalize the instance creation process. Following the successful launch of the instance, I established an SSH connection to it using the key pair obtained from AWS during the instance creation phase.

### 2.2 Clone the repository on the linux server
- To ensure seamless hosting on AWS and accommodate all future changes from Git, it was imperative to clone the Git repository onto the instance.
- This was achieved by executing the "git clone" command, followed by pasting the SSH address copied from GitHub. This process effectively replicated the repository onto the EC2 instance.

### 2.3 Install a web server on EC2 
- To host the website on ec2 , i used the apache http server, for site hosting
- following the steps outlined in the note, I installed httpd, initiated its start, and enabled it to host the downloaded website template on the EC2 instance.

### 2.4 Configure httpd for the website
- To host the website using Apache, it's crucial to direct httpd to the directory containing the website template.
- This is accomplished by executing the command "sudo cp ~/MarketPeak_Ecommerce/* /var/www/html/", which copies the files from the specified directory to the httpd structure, enabling httpd to host the website.
-  Once this step is completed successfully, the next task is to verify that the hosted website can be accessed.
-  To do so, the public IP address of the EC2 instance, was manually copied and pasted directly into a web browser's address bar, to successfully  access to the downloaded template.

  ### Continuous Integration and Deployment workflow
  - I terminated the ec2 terminal
  - Created a new branch on the remote repository  named 'development'
  - Switched to the developement branch
  - Commited my changes with comment
  - Pushed the changes to github - origin
  - Switched back to main branch
  - Merged the development branch with the main
  - Pushed the changes back to the origin
  - For the changes to be pull into the product environment
  - I opened a new ec2 instance, and connected using ssh
  - Pulled the changes using 'git pull origin main'
  - Reloaded my apache2
  - Then tested the changes
  - It works again!
  - End


    ### Challenges:
    I encountered a challenge,trying to create the 'development branch', to resolve this I manually created the branch on github, by following the following steps;
    - Navigate to the Repository: I Opened the repository on GitHub where I want to create the new branch.
    - Navigated to the Branch Dropdown: At the top of the repository's page, there's  a dropdown menu that displays the current branch name. I clicked on this dropdown menu.
    - Entered the  Branch Name - 'development'
    - Created the Branch: After typing the branch name, I pressed Enter, and GitHub automatically  created the new branch for you.

      Challenge (2):
     - I encountere an error, trying to run the 'git push origin development', to resolve this, I ran the 'git pull origin development' command first. This command  workflow allows me to manage changes locally and then push them to the remote repository on GitHub when ready.

