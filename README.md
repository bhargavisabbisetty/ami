# CSYE 6225 - Spring 2020
# AMI - Packer

## Team

### Name: Vishnu Bhargavi Sabbisetty
### NUID: 001497937
### Github ID: bhargavisabbisetty
### Email id: sabbisetty.v@husky.neu.edu

## Technology Stack

* Shell Script


## Build Instructions

1. Clone the project using ` git clone git@github.com:bhargavisabbisetty/ami.git`
2. Follow the steps in the link to install packer: 
[Packer Installation Steps for Ubuntu](https://howtoprogram.xyz/2016/11/29/install-packer-ubuntu-16-04-1-lts-xenial-xerus/)

* For MacOS users do:

```sh
brew install packer
```

3. Navigate to folder ` ami `
4. Validate packer template

```sh
packer validate ubuntu-ami.json
```

5. Build AMI

```sh
packer build \
    -var 'aws_access_key=REDACTED' \
    -var 'aws_secret_key=REDACTED' \
    -var 'aws_region=us-east-1' \
    -var 'subnet_id=REDACTED' \
    ubuntu-ami.json
```

or 

```
packer build -var-file=./vars.json ubuntu-ami.json
```

## Deploy Instructions
* Go to aws console and launch EC2 instance with generated AMI image

## Running Tests

## CI/CD