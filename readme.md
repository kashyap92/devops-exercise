# Steps to set up Jenkins:
1. Clone `git clone https://github.com/kashyap92/devops-exercise.git`
2. `cd devops-exercise`
3. Build Jenkins image `docker build -t myjenkins:latest .` --> this will download and install all required plugins and amdin page is skipped.
4. Run Jenkin image 
`docker run --rm -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock myjenkins:latest`
5. `chmod 666 /var/run/docker.sock`

# Steps to setup jobs:
1. Create 2 pipeline jobs; upstream jobs can be any name but downstream job should be 'devops-exercise-downstream-job'
2. For the upstream job, use 'Jenkinsfile-upstream'.
3. For the 'devops-exercise-downstream-job' job use 'Jenkinsfile-downstream'.
4. For shared library, use 'Jenkinsfile-sharedlib' job, the shared libraries are located in a separate repo(standard/recommended configuration) in https://github.com/kashyap92/jenkins-shared-library.git
