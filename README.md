
# 2048 Game Docker Deployment

This repository provides a Docker setup for deploying the 2048 game. The Dockerfile sets up an Ubuntu container with Nginx to serve the game.

## Tools Used
- Docker
- Nginx
- Ubuntu 22.04
- GitHub (for the game source)
- AWS Elastic Beanstalk (for deployment)
- Render (for hosting)

## Dockerfile Overview
The Dockerfile performs the following steps:
1. Uses the ubuntu:22.04` base image.
2. Installs Nginx, 'zip' and `curl`.
3. Configures Nginx to run in the foreground.
4. Downloads and extracts the 2048 game source code from GitHub.
5. Moves the extracted files to the Nginx web root and removes the temporary files.
6. Exposes port 80 for web traffic.
7. Starts Nginx with the custom configuration.

## How to Build and Run Locally
1. Clone this repository:
   
      "git clone https://github.com/yourusername/2048-Game-Docker.git"
   
      cd 2048-Game-Docker

2. Build the Docker image:
 
      docker build -t 2048-game .

3.Run the Docker container:

  docker run -d -p 80:80 2048-game

4.Access the game at "http://localhost:80"




## Deployment to AWS Elastic Beanstalk

1. Install the AWS CLI and configure it with your AWS credentials.
2. Install the Elastic Beanstalk CLI .
3.Initialize an Elastic Beanstalk application:

    eb init

   
4.Create an Elastic Beanstalk environment:

  eb create --single
5. Deploy the Docker container:

   eb deploy


# Live Demo

The Docker image has been deployed and is available at: "https://two048-game-89gb.onrender.com"






