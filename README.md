# IaC-with-Terraform

using Terraform (a tool used to provision your cloud infrastructure) to create, update, and destroy Google Cloud resources. This tutorial will give you a breakdown of the steps.



<h2>Environments and Technologies Used</h2>

- Google Cloud Platform
- Terraform



<h2>Operating Systems Used </h2>

- mac OS Catalina 10.15.7

<h2>Configuration Objectives</h2>

- create a VM instance without mentioning network to see how terraform parses the configuration code
- edit the code to add network and create a VM instance on Google Cloud
- explore how to update the VM instance
- edit the existing configuration to add tags and then edit the machine type
- execute terraform commands to destroy the resources created
  
 

<h2>Configuration Steps</h2>

<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/8246850b-b7f2-4ffe-85ea-95eb5cf50830"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Once you are in active cloudshell, run the "terraform -- version" command to observe what version of terraform is currently running 
</p>
<br />

<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/a7599101-2ee3-47e8-920c-ec7782133774" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a main.tf file by running the "touch main.tf" command in cloud shell. 
</p>
<br />

<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/5de5b65c-c786-431f-a2d1-79f1674480c3"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here you can see the main.tf file has been created. Now we can add our coding to this file.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/9e094ff1-a5f9-4f1c-a9dc-8df9c7b98e30"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Run terraform init... as you can see terraform has been successfully initialized.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/fc90d89f-7959-414a-87d9-3c0177a4dbe0"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
There is an error when running terraform plan because you can't configure a compute engine without a network.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/27af60ce-5aeb-4c60-b9b8-e74723e845f2"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we can run terraform plan and should have no errors once executing the command.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/4231f16f-8965-47d6-9bc5-cea107fd1746"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  As you can see we successfully ran terraform plan and the network has also been added.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/94d50d4d-41c9-4c88-94e1-53ba6922935c"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Here we have added the network tags 'web and dav' to the instance, next we will edit the machine-type.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/7b3ad5db-e55f-4af3-9577-b09b368f73fb"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is what you should see after running terraform plan, you can see that the tags 'web and dav' has been added to the instance or VM
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/2c32486c-6412-470a-8dbb-0b73b350d4d4"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Our terraform compute instance has been created successfully in the compute engine.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/e85d4937-82a0-4557-b122-1a62c86298ea"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we have changed the machine type from e2-micro to e2-medium
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/603fad3e-47d7-4cce-8fe5-91fc34d8c8e9"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Now we run terraform plan, and we can see that terraform will execute the changes that we want. Next we run terraform apply.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/0a17272e-5189-4a63-9480-47aca8e589f7"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Terraform apply fails because the machine-type cannot be changed on a running VM. To ensure the VM stops before updating the machine-type, we set allow_stopping_for_update argument to true (shown at the bottom). 
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/IaC-with-Terraform/assets/146133122/fbbd0d48-d86a-434f-a2e7-9f9b0753111c"
height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Once the machine type has been successfully modified we can go ahead and destroy the instance by running terraform destroy. 
</p>
<br />
