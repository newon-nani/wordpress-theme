# Dockerized WordPress Theme Deployment

This guide will walk you through the process of creating a custom WordPress theme, building and launching it using Docker, and automating the deployment with GitHub Actions.

## Step 1: Create a Folder for Your Project


mkdir docker-wordpress-theme
cd docker-wordpress-theme

## Step 2: Creating a Custom WordPress Theme

Copy code
cd docker-wordpress-theme
composer create-project roots/sage

## Step 3: Install Node.js and npm

Copy code
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
source ~/.bashrc
nvm install 18.0.0
nvm use 18.0.0
nvm alias default 18.0.0
node -v
npm -v

## Step 4: Install Yarn

Copy code
npm install --global yarn
yarn --version

## Step 5: Building and Launching a Custom WordPress Theme

Copy code
cd ./sage
yarn add node-sass
yarn build

## Step 6: Automating Deployment with GitHub Actions

Create a .github/workflows directory in the root path.
Create a deploy.yml file and define the deployment procedure.

## Step 7: Create Secret Variables in Repository Settings

DEPLOY_KEY: Create SSH keys and add id_rsa.pub key into authorized keys of a VPS server. Add id_rsa key as secrets in your repository settings.
DOCKER_THEME_FOLDER: Paste the content-related paths of the Docker container.
SOURCE_CONTENT: Paste the path of the source files on the VPS server.
THEME_CONTENT: Paste the destination path on the server to transfer files.

## Step 8: Configure GitHub Actions

Copy the content from your deploy.yml file to the GitHub Actions workflow file, then commit and push to trigger the deployment process. Your WordPress theme will be built, and generated artifacts will be transferred to the server and copied to the WordPress container.

Now, your custom WordPress theme is ready for deployment and automated with GitHub Actions.
