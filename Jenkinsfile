// Filename: Jenkinsfile
node {
  def GITREPOREMOTE = "https://github.com/siddharth123/databricks_demo.git"
  def GITBRANCH     = "main"
  def DBCLIPATH     = "/home/linuxbrew/.linuxbrew/bin/databricks"
  def JQPATH        = "/usr/bin/jq"
  def JOBPREFIX     = "jenkins-demo"
  def BUNDLETARGET  = "dev"

  stage('Checkout') {
    git branch: GITBRANCH, url: GITREPOREMOTE
  }
  stage('Validate Bundle') {
    sh """#!/bin/bash
          ${DBCLIPATH}/databricks bundle validate -t ${BUNDLETARGET}
       """
  }
  stage('Deploy Bundle') {
    sh """#!/bin/bash
          ${DBCLIPATH}/databricks bundle deploy -t ${BUNDLETARGET}
       """
  }
}
