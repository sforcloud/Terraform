# Build Infrastructure

We'll build infrastructure on AWS for the getting started guide since it is popular and generally understood, but Terraform can manage many providers, including multiple providers in a single configuration

# Configuration

The set of files used to describe infrastructure in Terraform is simply known as a Terraform configuration. 

The entire configuration is shown below. We'll go over each part after. Save the contents to a file named *example.tf*. Verify that there are no other **.tf* files in your directory, since Terraform loads all of them


## Providers

The provider block is used to configure the named provider, in our case "aws". A provider is responsible for creating and managing resources. A provider is a plugin that Terraform uses to translate the API interactions with the service. A provider is responsible for understanding API interactions and exposing resources. Because Terraform can interact with any API, almost any infrastructure type can be represented as a resource in Terraform.

## Resources

The resource block defines a resource that exists within the infrastructure. A resource might be a physical component such as an EC2 instance, or it can be a logical resource such as a Heroku application.

The resource block has two strings before opening the block: the resource type and the resource name. In our example, the resource type is "aws_instance" and the name is "example." The prefix of the type maps to the provider. In our case "aws_instance" automatically tells Terraform that it is managed by the "aws" provider.

## Initialization

The first command to run for a new configuration -- or after checking out an existing configuration from version control -- is terraform init, which initializes various local settings and data that will be used by subsequent commands.

```sh
terraform init
```

## Formatting and Validating Configurations


The terraform fmt command enables standardization which automatically updates configurations in the current directory for easy readability and consistency.
```sh
terraform fmt
```

If you are copying configuration snippets or just want to make sure your configuration is syntactically valid and internally consistent, the built in terraform validate command will check and report errors within modules, attribute names, and value types.

```sh
terraform validate
```

## Apply Changes
```sh
terraform apply
```

```sh
terraform show
```
## Manually Managing State

Terraform has a built in command called *terraform state* which is used for advanced state management. In cases where a user would need to modify the state file by finding resources in the *terraform.tfstate* file with *terraform state* list. This will give us a list of resources as addresses and resource IDs that we can then modify.
