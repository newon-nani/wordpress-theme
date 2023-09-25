# Dockerized WordPress Theme Deployment using Github actions ci/cd

This guide will walk you through the process of creating a custom WordPress theme, building and launching it using Docker, and automating the deployment with GitHub Actions.

## Step 1: Clone the repository

## Step 2: Install Dependencies on vps server
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
source ~/.bashrc
nvm install 18.0.0
nvm use 18.0.0
nvm alias default 18.0.0
node -v
npm -v
npm install --global yarn
yarn --version
```
## Step 3: Build and generate a Custom WordPress Theme
```sh
cd ./sage
yarn add node-sass
yarn build
```

## Step 4: Store Secret Variables in Repository Settings

DEPLOY_KEY: Create SSH keys and add id_rsa.pub key into authorized keys of a VPS server. Add id_rsa key as secrets in your repository settings.<br>
DOCKER_THEME_FOLDER: Paste the content-related paths of the Docker container.<br>
SOURCE_CONTENT: Paste the path of the source files on the VPS server.<br>
THEME_CONTENT: Paste the destination path on the server to transfer files.

## Step 5: Configure GitHub Actions

just a sample changes and commit now to trigger the deployment process. Your code will be built and generates the artifacts, then they were transferred to the server in cd process and copied to the WordPress container.

Now, your custom WordPress theme Deployment setup using Github actions is ready for use:)
