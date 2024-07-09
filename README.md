# Kura Labs Cohort 5- Deployment Workload 1
## Intro to CI/CD

Welcome to Deployment Workload 1!  By now you’ve learned about system designs and the CI/CD Pipeline.  Let’s start putting it all together and see it in action.  

Be sure to document each step in the process and explain WHY each step is important to the pipeline.

# Instructions

1. Fork this repository to your GitHub account
2. Create an EC2

	a. Follow document: AWS EC2 Quickstart Guide if needed
3. Install Jenkins onto the EC2

	a. Connect to the EC2 terminal

 	b. Enter the following commands to install Jenkins:


		$sudo apt update && sudo apt install default-jre python3-pip python3.10-venv
		$sudo wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo gpg --batch --yes --dearmor -o /usr/share/keyrings/jenkins.gpg
		$sudo sh -c 'echo deb [signed-by=/usr/share/keyrings/jenkins.gpg] http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
		$sudo apt update && sudo apt install jenkins -y
		$sudo systemctl start jenkins
		$sudo systemctl status jenkins
If successful, the last command should show the Jenkins service “active (running)”

4. Log into Jenkins

	a. Enter initial admin password

	b. Install suggested plugins

	c. Create first admin user

5. Create a Multi-Branch pipeline

	a. Click on “New Item” in the menu on the left of the page

	b. Enter a name for your pipeline

   	c. Select “Multibranch Pipeline”

	d. Under “Branch Sources”, click “Add source” and select “GitHub”

  	e. Click “+ Add” and select “Jenkins”

	f. Make sure “Kind” reads “Username and password”

	g. Under “Username”, enter your GitHub username

	h. Under “Password” ,enter your GitHub personal access token

To get the GitHub personal access token, first log into GitHub and click on your profile icon on the top right of the page. 

i. On the dropdown menu, click on “Settings”

ii. Click on “<> Developer settings at the bottom of the menu on the left of the page

iii. Click on “Personal access tokens” on the menu on the left of the page and select “Tokens (classic)”

iv. Click “Generate new token” and select the classic option

This token can only be viewed ONCE! Make sure you enter the token properly before leaving the page otherwise a new token must be generated!

6. Connect GitHub repository to Jenkins

	a. If successful, a build should start automatically

Did the build stages successfully complete? If not, why? How did you resolve the issue?  What did each stage do? 

7. After successfully completing the build (provide screenshot of successful build in documentation), download the contents of the repository (the one in your personal GitHub NOT the kuralabs repo!) as a zip file and upload it to AWS Elastic Beanstalk.
