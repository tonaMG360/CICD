#!/usr/bin/env groovy

pipeline {
    //agent { dockerfile true }
    agent any 
    tools {nodejs "latest"}
    
    stages{
        stage('preflight') {
            steps {
                echo sh(returnStdout: true, script: 'env')
                sh 'node -v'
            }
        }

        stage('build') {
            steps {
                sh 'npm --version'
                sh 'npm install'
                sh 'chmod u+x app.js'
            }
        }

        stage('Test') {
            steps {
                sh 'node --version'
            }
        }

        stage('deployWebsite'){
            steps{
                sh 'nodemon ./app.js'
            }

        }