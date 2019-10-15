pipeline {
    agent any
    stages{
        stage('clone the repo and removing the existing one')
        {
          steps {
              sh "sudo rm -rf /home/susanne/project"
              sh "cd /home/susanne/"
              sh "mkdir -p /home/susanne/project"
              sh "cd /home/susanne/project"
              sh "git clone https://github.com/PacktPublishing/Develop-and-Deploy-Modern-Web-Applications-with-Docker-Video-.git /home/susanne/project"
               
               }
         }
         
         stage("copying files to /var/www/html")
         {
           steps 
           {
              sh "sudo cp /home/susanne/project/www/html/index.html /var/www/html/"
           }
          }
          
           stage("Installing the webserver and starting its service")
          {
            steps
            {
              sh "sudo apt install apache2 -y"
              sh "sudo systemctl start apache2"
            }
          }
          
          
          stage("Restarting the apache2 service")
          {
            steps
            {
              sh "sudo systemctl restart apache2"
            }
          }
               
    }

}
