# ShoppingWeb
# ShoppingWeb

jenkin : Harshita - d4528f056d9545a8928aab4567bb42de
docker : harshitap6
Jenkin steps- html css files create ..... push to github (dont add readme files) .....open jenkin (usually localhost:8080)- new item - pipeline - ok .....github repo---github hook trigger for gitscm polling  check ---pipeline script --- done


git init
git add .
git commit -m "Initial commit of portfolio website"
git branch -M main
git remote add origin https://github.com/your-username/my-portfolio.git
git push -u origin main


pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Harshigit28/portfolio-repo.git'
            }
        }
        stage('Deploy') {
            steps {
                bat 'xcopy /E /I /Y "%WORKSPACE%\\*" "C:\\inetpub\\wwwroot\\portfolio\\"'
                // Adjust the destination path to your actual deployment folder
            }
        }
    }
}


Using  Docker 
1) Github push  
2)Dockerfile :
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 

3)docker build -t travel-agency-website:v1 .

4)docker run -d -p 8080:80 travel-agency-website:v1

Using Maven 
mvn archetype:generate -DgroupId=com.myblog -DartifactId=MyBlog -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false
2) create html files in MyBlog/src/main/webapp/css/style.css
3)create css in MyBlog/src/main/webapp/css/style.css
4)create web.xml 
5)update pom.xml as needed 
6)mvn clean
mvn compile
mvn package
7)use jetty in pom to run locally 
