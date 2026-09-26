# terraform-aws-vpc

## Overview
This terraform modules create an AWS VPC with a given CIDR 
block. It also creates multiple subnets (pubic and private), 
and for public subnets, it sets up an Internet Gateway (IGW)
and appropriate route tables.

## Features
- Creates a VPC with specified CIDR block
- Creates public and private subntes
- Creates an Internet Gateway (IGW) for public subnets
- Set up route tables for public subnets

## Usage
''' 
provider "aws" {
  region = "ap-south-1"
}

module "vpc" {
  source = "./vpc"

  vpc_config = {
    cidr_block = "10.0.0.0/16"
    name       = "our-vpc-name"
  }
  subnet_config = {
    public_subnet- = {
      cidr_block = "10.0.0.0/24"
      az         = "ap-south-1a"
      public     = true
    }
    private_subnet = {
      cidr_block = "10.0.1.0/24"
      az         = "ap-south-1b"
    }
  }
}

'''
