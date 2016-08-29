HOL 0 - Set up Parts Unlimited MRP
====================================================================================

In this lab, we will set up the PartsUnlimited MRP VSTS team project as a pre-requisite for the Continuous Integration lab. 

### Pre-requisites

-   An active Visual Studio Team Services (VSTS) account
	> You will need an active Visual Studio Team Services (VSTS) account already, or you will need to sign up for a free Visual Studio Team Services account by following [this link.](https://www.visualstudio.com/en-us/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services) Alternatively, you can follow the steps in _Create a Visual Studio Team Services (VSTS) Account_ in Lab 1 of the **DEV212x: Intro to DevOps** course found [here](https://github.com/MicrosoftLearning/edX-DEV212x-Intro-to-DevOps/blob/master/docs/Lab1/edX-DEV212x-Lab1.md). 

-   Project Collection Administrator rights to the Visual Studio Team Services account
	> If you are not a Project Collection Administrator for the Visual Studio Team Services account, follow the instructions at [this link.](https://www.visualstudio.com/en-us/docs/setup-admin/add-administrator-tfs#project-collection). Alternatively, you can follow the steps above to create a new VSTS account. You will, by default, be an administrator of your own account.

- 	Git
	> If you are running Linux on your local workstation, install git with "sudo apt-get install git". 
	If you are running Windows, you can install the git client from [http://git-scm.com/download](http://git-scm.com/download).
	
### Tasks Overview

**Set up your Visual Studio Team Services account:** This step helps you download the source code, and then push it to your own Visual Studio Team Services account.

## Task 1: Configure your Visual Studio Team Services account

We want to push the application code to your Visual Studio Team Services account in
order to use Team Build for the Continuous Integration HOL.

**1.** First, navigate to your Visual Studio Team Services account by typing into a browser: 

    https://{VSTS instance name}.visualstudio.com

**2.** Once at your Visual Studio Team Services account, create a new PartsUnlimitedMRP team project by clicking on the **New** button under **Recent projects & teams**. Type in the project name as *PartsUnlimitedMRP* and select *Git* as the version control, then click on **Create project**.

![](<media/create_team_project.png>)

**3.** After the wizard creates your new team project, navigate to the PartsUnlimitedMRP team project and click on the **Code** tab on the upper-left. 

![](<media/navigate_to_code.png>)

**4.** The PartsUnlimitedMRP Git repository will be empty, so copy the Clone URL of the VSTS repository to your clipboard and paste it into a text document for use later. 

![](<media/copy_vsts_repo_url.png>)

**5. (Optional)** There are a few Git providers that only support Basic Auth. If you are using one of those providers, 
you will need to set up either alternate credentials in Visual Studio Team Services (VSTS) or use a personal access token (PAT).
 Of the two, PATs are recommended for tighter security. Follow the steps in this [link](https://www.visualstudio.com/en-us/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate) 
 to create a personal access token (PAT). A PAT is a secure mechanism for controlling access to your VSTS account. If you skip this step, and your Git provider supports it, you can simply authenticate to VSTS using your username and password.

> This Personal Access Token (PAT) will be used when interacting with the Git repository from the
command line. Make sure you copy the token now. Visual Studio Team Services does not store it and you won't be able to see it again. 

> It is strongly recommended to install the [Git Credential Manager for Mac or Linux](https://github.com/Microsoft/Git-Credential-Manager-for-Mac-and-Linux) or [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows) to simplify authentication when using Git.  

**6.** Clone the **PartsUnlimitedMRP** git repository located in GitHub onto your local machine:

    git clone https://github.com/Microsoft/PartsUnlimitedMRP.git

![](<media/clone_mrp.png>)

**3.** Add the Clone URL of your Visual Studio Team Services repository as a new remote called **vsts** and push to it
your Visual Studio Team Services account. While pushing, use any username without the "@" symbol and the PAT that you copied as the password. (Alternatively, you can enter your VSTS username and password.)

	cd PartsUnlimitedMRP/

	git remote add vsts <url_to_repository>

	git push -u vsts --all
	
![](<media/push_to_vsts.png>)

> We added the Visual Studio Team Services repository as a remote named **vsts**, so we need to
push to that remote in the future for our changes to appear in our Visual Studio Team Services
repository.

**4.** Your Visual Studio Team Services account should now have a copy of the PartsUnlimitedMRP
application:

![](<media/mrp_in_vsts.png>)
 

Next steps
----------

In this lab, you learned how to set up the PartsUnlimitedMRP team project in Visual Studio Team Services. Try these labs out for next steps:

-   [Parts Unlimited MRP Continuous Integration](https://github.com/MicrosoftLearning/edX-DEV217x-DevOps/tree/master/docs/Module4Labs/HOL_Continuous-Integration)

-   [Parts Unlimited MRP Continuous Deployment](https://github.com/MicrosoftLearning/edX-DEV217x-DevOps/tree/master/docs/Module4Labs/HOL_Continuous-Deployment)

-   [Parts Unlimited MRP Application Performance Monitoring](https://github.com/MicrosoftLearning/edX-DEV217x-DevOps/tree/master/docs/Module5Labs/HOL_Application-Performance-Monitoring)

-	[Deploying PartsUnlimitedMRP using Chef](https://github.com/MicrosoftLearning/edX-DEV217x-DevOps/tree/master/docs/Module2Labs/HOL_Deploying-Using-Chef)
