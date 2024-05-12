Terraform: it is an infrastructre as a code, i.e is managing and provisioning of infrastructure through code instead of using manual process to configure th
Features: 
  --> uses HCL language 
  --> this is not integrated with any cloud platform
  --> we can use or integrate with any cloud platform by providing the required providers
  --> can be included in ci/cd as well.
  
Architecture: main.tf file (where we mention all the configuration details)

for installing terraform we need to download the terraform exe file
https://www.terraform.io/



after this in cmd search for terraform version --> if this shows that this is not an internal command then set the env variables path 

  --> we can use terraform for better suggestions by installing the plugin in vs code
  
for running the script we have mainly 4 commands which we use --> there are other commands as well 
  1. terraform init   --> it initilazes the project (creates a directory in .terraform/plugins/registery.terraform.io
  2. terraform paln   --> will check any other resource groups or any other are involved or not(basically shows a dry run for us) 
  3. terraform apply  --> after perfroming dry run it creates the required source or shows error if any occurs.
  4. terraform delete --> to delete the resources
  
 tfstate file -->we store our data i.e ip's and other things 
   --> if multiple dev are using tfstate files the we store our tfstate file in our backend i.e in our blobstorage/git repo/s3
   --> it will record all the changes happening in the terraform 
### interview question ####
how do we configure multiple cloud providers in terraform?
A: for multiple cloud providers we provide a param called "parameter" and we mention the cloud providers here


variables: these are to parameterize the values (lets say if we want the same requirment for diff teams we can write the script and parmaterize them).
  2types of variables: 1). Input variable 2). Output variables
    Input variables: to pass some value/information from the user end to terraform
	Ouput variables: to provide output for the user from terraform like after execuing the commands ip's and other details etc..
  we maintian all the variables in one file name called terraform.tfvars file 
  -->we can also change the name for .tfvars file  but we need to provide the path of the file at the time of execution 
  
  we need to provide variables at the top in main.tf file 
  and we need to mention each an every value for the vaiables which we want to add, we pass the values in "terraform.tfvars" file.
   
  Modules:
  
  we can create all the differnet files for each and every module, like we can split the main.tf file in many ways like 
   if we want variable then we create "variable.tf" 
   for providers we can create "provider.tf" 
   and values of variables  "terraform.tfvars"
   
 
