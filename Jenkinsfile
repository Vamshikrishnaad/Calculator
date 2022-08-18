pipeline
{
    tools
    {
        jdk 'myjava'
        maven 'mavenlatest'
    }
    
    agent any
        stages('Build Stage')
        {
            stage('Clone the Repo')
            {
                steps
                {
                    git 'https://github.com/HouariZegai/Calculator.git'
                }
            }
            
            stage('Code Review')
            {
                steps
                {
                    sh 'mvn pmd:pmd'
                }
            }
            
            stage('Testing')
            {
                steps
                {
                    sh 'mvn test'
                }
            }
            
            stage('Code Coverage')
            {
                steps
                {
                    sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
                }
            }
            
            stage('Package artifact')
            {
                steps
                {
                    sh 'mvn package'
                }
            }
        }
}
