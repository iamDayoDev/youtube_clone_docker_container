## Containerizing a Youtube Clone Using Docker

## STEPS TO FOLLOW:

### STEP 1: Create an EC2 Instance
- Log into your AWS account  and create an EC2 with necessary networking and security configurations.
- SSH into the instance.

### STEP 2: Install Docker
- Use `sudo apt update -y` to update necessary packages on your EC2
- Run `sudo apt install docker.io -y` to install docker
- To give required permission to the user, rune `sudo usermod -aG docker ubuntu`
- Restart your EC2

### STEP 3: Clone this Repository
`git clone https://github.com/iamDayoDev/youtube_clone_docker_container.git`

- Chnage directory into the folder that contains the source code
`cd youtube-clone-docker`

### STEP 4: Build your Docker image
Run `docker build -t [preferred_name you want for your image] .`

### STEP 5: Run the Container.
To run the container, run this command
`docker run -p 9090:3000 -it [docker-image-name]`

## P.S Make Sure you set your inbound rules on your EC2 security group to allow traffic on port 9090

## You have successfully deployed a containerized app on AWS EC2 instane. 

# Alternatively

## You can deploy this app using terraform.
- Clone the repo and do terraform apply to provision an EC2 intance and install docker packege automaically using the `docker-install.sh` file.

