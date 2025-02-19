# HaitiHealthBox
An all-inclusive health information system setup for health facilities in Haiti

# Setup Instructions

## Step One: Install Docker
See https://docs.docker.com/engine/install/

Test to make sure both of these commands work:
```sh
docker -v
docker compose version
```

**Note: If your docker version does not support the `docker compose` syntax, 
install `docker-compose` using the instructions here: https://docs.docker.com/compose/install/**


## Step Two: Get HaitiHealthBox from GitHub

Run the following command:
```sh
git clone https://github.com/I-TECH-UW/HaitiHealthBox.git
```

If you want to use a specific version from the [version list](https://github.com/I-TECH-UW/HaitiHealthBox/releases), you can check out the corresponding tag. For example, to use version `0.0.0-alpha`, run:
```sh
git checkout v0.0.0-alpha
```

Otherwise, you can use the latest `main` branch that is the default. 

## Step Three: Set some configurations
Set some temporary variables to store your desired iSantePlus Database and iSantePlus admin passwords:

```sh
export IPLUS_ADMIN_PW=<your-password>
export IPLUS_DB_PW=<your-password>
```
## Step Four: Boot up Docker Enviornment
Navigate to the `HaitiHealthBox` directory on your machine and run the following command:
```sh
docker-compose up -d
```

## Local setup

Spin up the services

```
docker-compose -f docker-compose.local.yml up -d
```

Acces the services at 

| Instance  |     URL       | credentials (user : password)|
|---------- |:-------------:|------:                       |
| Isanteplus   |  https://localhost/openmrs/login.htm  | admin : Admin123 |
| OpenHIM   |    https://localhost/  |  root@openhim.org : admin |
| OpenELIS | https://localhost/OpenELIS-Global/ |    admin : adminADMIN!| 

## Instructions 
1. Add the necesary Lab Unit permisions to the User      
Go To `Admin -> User Management -> Select User -> Under "Roles" ,Choose "ALL Lab Units" and select  "All Permissions"`

2. Enable Importing electronic orders       
Go To `Admin -> Order Entry Configuration -> Select "external orders" -> Click "Modify" -> select "True"`

3. Add the Right Test Catalogue ie tests with `Loinc Codes`

see [more](https://i-tech-uw.github.io/healthinformationexchange/lis-workflows/lis-workflows.html#tutorial-lab-order-communication-between-openmrs-and-openelis) for the EMR-LIS communication


