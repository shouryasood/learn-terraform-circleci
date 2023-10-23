1. Create Terraform Cloud Token :
    A. Login to Terraform Cloud
    B. Open ORGANIZATION SETTINGS > TEAMS > TEAM API TOKEN > VREATE A NEW TOKEN
    C. Copy the token as it won't be shown again.

2. Fork & Clone a web app from GitHub to your working server.
    $ git clone https://github.com/USER_NAME/REPO_NAME

3. Write Terraform Code to deploy the web app in REPOSITORY on s3 Bucket.

4. Write CIRCLE-CI jobs in .CIRCLECI-->config.yml file in your current directory.

5. Configure Circle CI with Github :
    A. Generate SSH key in your workin machine/server. $ssh keygen -t ed25519 -f ~/.ssh/project_key -c yourEmail@domain.com
    B. Copy PUBLIC Key from your machine (C:/Users/USER_NAME/.ssh/project_key.pub) to ITHUB in : REPO SETTINGS > DEPLOY KEYS
    C. Copy PRIVATE kry from your machine (C:/Users/USER_NAME/.ssh/project_key) to Circle CI when making a new project

6. In Circle CI, go to PROJECT SETTINGS > ENVIORNMENT VARIABLES and set your 
    AWS SECERETS :
        AWS_ACCESS_KEY_ID
        AWS_SECERET_ACCESS_KEY
    Terraform SECERETS : 
        TF_CLOUD_ORGANIZATION - Terraform organization name
        TF_WORKSPACE - Terraform workspace name
        TF_TOKEN_app_terraform_io - created in step 1 

7.TRIGGER CI/CD in your local system.
    $git add *
    $git commit -m "messageone"
    $git push
