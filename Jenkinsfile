pipeline {
    agent any

    tools {
        maven "maven"
    }
    
  // parameters {
     //   string(name: 'company', defaultValue: 'Sapient', description: 'Enter your cmopany name???')
//	booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: 'do you want to buidl with debug')
//	choice(name: 'env', choices: ['DEV', 'TEST', 'PROD'], description: 'specify you build env') 
  //  }

    stages {
                stage('Install') 
                {
                            steps {
                        


                                git 'https://github.com/prateekkaushal123/testjenkins2.git'

                                // Run Maven on a Unix agent.
                                sh "mvn -Dmaven.test.failure.ignore=true clean install"

                                }

                }

                stage('Build') 
                {
                    steps 
                    {
                

                        // Run Maven on a Unix agent.
                        sh "docker image build -t testjenkins2 ."

                    }

                }

                stage('Deployement') 
                {
                    steps {
                
                        // Run Maven on a Unix agent.
                        sh "docker run testjenkins2"

                            }
                }

  

}

}