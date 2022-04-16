# terraform-server


terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "4.10.0"
    }
  }
}
provider "aws" {
  profile = "default"
  region  = "ap-south-1" 
}
resource "aws_instance" "app_server" {
  ami           = "ami-0d2986f2e8c0f7d01"  
  instance_type = "t2.micro"      

  tags = {
    Name = "ExampleAppServerInstance"
  }
