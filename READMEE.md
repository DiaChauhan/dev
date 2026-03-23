🔥 1. JENKINS BASIC (Freestyle Job)
🪜 Steps
1. Open Jenkins → http://localhost:8080
2. Click New Item
3. Enter name → Select Freestyle Project → OK
4. Scroll to Build
5. Add Build Step → Execute Windows Batch Command
6. Write command
7. Save → Build Now
8. Click build → Console Output
💻 Code
echo Hello Jenkins
________________________________________
🔥 2. JENKINS PIPELINE
🪜 Steps
1. Click New Item
2. Select Pipeline → OK
3. Go to Pipeline section
4. Select "Pipeline script"
5. Paste script
6. Save → Build Now
7. Check Console Output
💻 Code
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building project..."
            }
        }
        stage('Test') {
            steps {
                echo "Testing project..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying project..."
            }
        }
    }
}
________________________________________
🔥 3. BUILD TRIGGER (4A / 4B)
🪜 Steps
1. Create Freestyle Job
2. Scroll to Build Triggers
3. Tick "Build periodically"
4. Add cron expression
5. Add Build Step (echo)
6. Save
💻 Code
H/2 * * * *
echo Auto Build Running
________________________________________
🔥 4. PARAMETERIZED PIPELINE (4C)
🪜 Steps
1. Create Pipeline Job
2. Add parameters section
3. Add cron trigger
4. Use parameter in echo
5. Save → Build
💻 Code
pipeline {
    agent any

    parameters {
        string(name: 'USERNAME', defaultValue: 'Student')
    }

    triggers {
        cron('H/2 * * * *')
    }

    stages {
        stage('Greeting') {
            steps {
                echo "Hello ${params.USERNAME}"
            }
        }
    }
}
________________________________________
🔥 5. JENKINS + MAVEN (5A)
🪜 Steps
1. Create Freestyle Job
2. Configure Git (optional)
3. Add Build Step → Invoke top-level Maven targets
4. Enter goal
5. Save → Build Now
💻 Code
clean install
________________________________________
🔥 6. JENKINS + ANT (5B)
🪜 Steps
1. Create Freestyle Job
2. Configure Git (optional)
3. Add Build Step → Invoke Ant
4. Enter target
5. Save → Build Now
💻 Code
build
________________________________________
🔥 7. DOCKER COMMANDS
🪜 Steps + Commands
docker --version

docker pull nginx

docker run -d -p 8080:80 nginx

docker ps

docker stop <container_id>

docker rm <container_id>

docker images
________________________________________
🔥 8. DOCKERFILE
🪜 Steps
1. Create file named Dockerfile
2. Add instructions
3. Build image
4. Run container
💻 Code
FROM nginx
COPY . /usr/share/nginx/html
Build + Run
docker build -t myapp .
docker run -d -p 8080:80 myapp
________________________________________
🔥 9. DOCKER ARCHITECTURE
Docker Client → Docker Daemon → Images → Containers
________________________________________
🔥 10. JENKINS MASTER-SLAVE
🪜 Steps
1. Go to Manage Jenkins
2. Manage Nodes and Clouds
3. Create New Node
4. Configure slave node
5. Connect to master
6. Run jobs on slave
________________________________________
🔥 11. SELENIUM + JENKINS
🪜 Steps
1. Create Jenkins Job
2. Add Maven Build Step
3. Integrate Selenium test scripts
4. Run job
5. Check results
________________________________________
🔥 12. PUPPET (BASICS)
🪜 Steps
1. Install Puppet
2. Create manifest file (.pp)
3. Define resources
4. Apply configuration
💻 Code
file { '/tmp/test.txt':
  ensure => present,
}
________________________________________
🔥 13. PUPPET LAMP / MEAN
🪜 Steps
1. Create Puppet manifest
2. Install Apache/MySQL/PHP
3. Apply configuration

