## This reposistory is created with learning purposes for Terraform, showing how to structure Terraform code.

## Purpose :

- It shows how Terraform parses its files and how a project can be strucutred.


## Terraform files :

- Terraform parses all the files in the working directory with extention `.tf` or `.tf.json`, all other files with different extentions are ignored.

- Overriding does not work in Terraform, each resource (for example AWS instance named "web") can be defined in only one of the `.tf` files. Overriding a resource from same type and with same name is going to result in an error.

- Which files are parsed by Terraform :
    ```shell
    ├── LICENSE
    ├── innerDir
    │   └── main.tf
    ├── main.tf
    ├── readme.md
    └── variables.tf
    ```
    In the example above terraform is going to parse the `main.tf` file and `variable.tf`, but not the `main.tf` file which is located inside the directory named `innerDir`.

## Terraform code strucutre : 

- There are various ways to structure Terraform code :

1. Having everyting in `main.tf` and addtional files to define variables and show outputs.
    ```shell
    ├── main.tf
    ├── outputs.tf
    ├── terraform.tfvars
    └── variables.tf
    ```
2. Organizing file by resources that they provide.
    ```shell
    ├── load-balancers.tf
    ├── instances.tf
    └── shared.tf
    ```
