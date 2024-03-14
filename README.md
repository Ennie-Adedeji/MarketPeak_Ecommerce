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
