# Terraform + Netlify Deployment
This project shows how to use Terraform to deploy a simple HTML site on Netlif, with Terraform state stored in HCP form.

#Prerequisites
Before running this project,make sure you have:

-[Terraform](https://developer.hashicorp.com/terraform/downloads) v1.6+
-A [Github account](https://github.com)
-A [Netlify account](https://app.netlify.com)
-A [HCP Terraform account](https://app.terraform.io)
-A Netlify personal Token(ensure to save Token)

##Step Up
1.Connect to HCP Terraform
-Create an Organization and a Workspace in HCP Terraform
-Create and Save your HCP Terraform API Token locally:
    '''bash
  terraform login
Terraform saves it to ~/.terraform.d/credentials.tfrc.json.

2.Set Netlify Credentials in an environment Variable
-Get your Netlify Personal Access Token from your Netlify account settings
-Configure your NETLIFY_TOKEN:
   '''bash
   export
NETLIFY_TOKEN="your_token_here".

3.Run Terraform inside the same folder
-terraform init
-terraform plan
-terraform apply
-Type yes when asked

Variables
-netlify_token = Netlify Personal Access Token

Outputs
-netlify_site_url = "htpps://your-site-name.netlify.app".........(The live link to your deployed netlify site)

4.Create a gitignore file with:
.terraform/*.tfstate*.tfstate.backup .terraform.lock.hclterraform.tfvars
-Commit it to Git.

5.Get Live Site Link with:
   bash
-terraform output netlify_site_url
