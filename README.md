# balu


# STEP 1: Update Ubuntu
sudo apt update && sudo apt upgrade -y

# STEP 2: Install Git
sudo apt install git -y

# STEP 3: Install Docker
sudo apt install docker.io -y

# STEP 4: Start Docker
sudo systemctl start docker
sudo systemctl enable docker

# STEP 5: Verify installations
git --version
sudo docker --version

# STEP 6: Clone GitHub repository
# Replace this URL with the correct working repository URL
git clone YOUR_CORRECT_GITHUB_URL

# STEP 7: Enter project folder
cd MetroRepo

# STEP 8: View project files
ls -la

# STEP 9: Create Dockerfile
nano Dockerfile

# STEP 10: Build Docker image
sudo docker build -t metrorepo .

# STEP 11: Run Docker container
sudo docker run -d --name metro-container -p 80:3000 metrorepo

# STEP 12: Check running containers
sudo docker ps

services:
  nginx:
    image: nginx:latest
    container_name: my-nginx
    ports:
      - "8080:80"

  postgres:
    image: postgres:latest
    container_name: my-postgres
    environment:
      POSTGRES_USER: admin
      POSTGRES_PASSWORD: admin123
      POSTGRES_DB: company
    ports:
      - "5432:5432"


services:
  mysql:
    image: mysql:8.0
    container_name: my-mysql
    environment:
      MYSQL_ROOT_PASSWORD: root123
      MYSQL_DATABASE: wordpress
      MYSQL_USER: admin
      MYSQL_PASSWORD: admin123

  wordpress:
    image: wordpress:latest
    container_name: my-wordpress
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: mysql
      WORDPRESS_DB_USER: admin
      WORDPRESS_DB_PASSWORD: admin123
      WORDPRESS_DB_NAME: wordpress
    depends_on:
      - mysql



# STEP 13: Check container logs
sudo docker logs metro-container
⁠
