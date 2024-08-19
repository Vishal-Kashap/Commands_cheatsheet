# Terraform Basic Commands

## Initialize Terraform
Before you can start using Terraform, you need to initialize your working directory. This command downloads the necessary provider plugins and prepares the backend.

```bash
terraform init
```

## Validate Terraform Configuration
Validate the configuration files in your directory. This command checks the syntax and verifies that it is correct.

```bash
terraform validate
```

## Plan Terraform Changes
Create an execution plan to see what changes will be made to your infrastructure. This command helps you understand the impact of your changes before applying them.

```bash
terraform plan
```

## Apply Terraform Configuration
Apply the changes required to reach the desired state of the configuration. This command makes the necessary changes to your infrastructure.

```bash
terraform apply
```

## Destroy Terraform-managed Infrastructure
Destroy the infrastructure managed by Terraform. This command will remove all resources defined in your configuration.

```bash
terraform destroy
```

## Format Terraform Configuration
Format your Terraform code according to the standard style conventions. This command automatically formats the configuration files in the directory.

```bash
terraform fmt
```

## Show Terraform State
Display the current state or a specific resource within the state file. This command allows you to inspect the current state of your infrastructure.

```bash
terraform show
```

## Refresh Terraform State
Refresh the state file with the real infrastructure state. This command updates the state file with the latest state from the remote infrastructure.

```bash
terraform refresh
```

## List Terraform State Resources
List all the resources in the current state file. This command is useful to see all the resources managed by Terraform in your environment.

```bash
terraform state list
```
<!-- 
## Import Existing Infrastructure into Terraform
Import existing infrastructure into your Terraform state. This command allows you to bring resources created outside of Terraform under Terraform management.

```bash
terraform import [resource_type.resource_name] [resource_id]
```
-->
## Rename a Resource in Terraform State
Rename a resource in the state file. This command is useful when you want to change the resource name in your configuration without losing its current state.

```bash
terraform state mv [old_resource_name] [new_resource_name]
```

## Remove a Resource from Terraform State
Remove a resource from the state file. This command is used when you want to stop managing a resource with Terraform without deleting the actual resource.

```bash
terraform state rm [resource_name]
```

## Output Terraform Variables
Display the values of output variables defined in your configuration. This command allows you to see the values of outputs after running `terraform apply`.

```bash
terraform output
```

## Taint a Resource
Mark a resource for recreation on the next `terraform apply`. This command is useful when you want to force Terraform to recreate a resource.

```bash
terraform taint [resource_name]
```

## Untaint a Resource
Remove the taint from a resource. This command is used to undo the taint, so the resource is not recreated on the next apply.

```bash
terraform untaint [resource_name]
```

## Plan and Save Execution Plan
Save the execution plan to a file. This command is useful if you want to review or apply the plan later.

```bash
terraform plan -out=plan.out
```

## Apply Saved Execution Plan
Apply the execution plan from a saved file. This command uses the previously saved plan to make changes to your infrastructure.

```bash
terraform apply "plan.out"
```

<!-- 
## Lock the State
Manually lock the state for exclusive operations. This command ensures that only one person can modify the state at a time.

```bash
terraform force-unlock [lock_id]
```
<!-- 
## Unlock the State
Force unlock the state if it gets stuck in a locked state. This command removes the lock manually.

```bash
terraform force-unlock [lock_id]
```
-->
## Get Terraform Modules
Download and update modules referenced in the configuration. This command fetches the latest version of modules used in your configuration.

```bash
terraform get
```

## Graph Terraform Resources
Generate a visual representation of the Terraform configuration and state. This command outputs a DOT format graph that can be used with visualization tools.

```bash
terraform graph
```

## Apply Only Specific Resources
Apply changes only to the specified resources. This command limits the scope of `terraform apply` to specific resources.

```bash
terraform apply -target=[resource_name]
```
<!-- 
## Terraform Workspaces
Create, select, and manage workspaces. Workspaces are used to manage different environments or stages of infrastructure.

- Create a new workspace:

```bash
terraform workspace new [workspace_name]
```

- Select an existing workspace:

```bash
terraform workspace select [workspace_name]
```

- List all workspaces:

```bash
terraform workspace list
```

- Delete a workspace:

```bash
terraform workspace delete [workspace_name]
```

## Terraform Remote Backend
Configure Terraform to store the state file remotely. Remote backends allow multiple team members to collaborate and ensure state consistency.

```hcl
terraform {
  backend "s3" {
    bucket = "mybucket"
    key    = "path/to/my/key"
    region = "us-east-1"
  }
}
```
-->
