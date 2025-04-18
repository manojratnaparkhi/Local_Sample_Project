pipeline {
            agent any
            environment {
                        NEW_VERSION='1.2.3'
                        SERVER_CREDENTIALS=credentials('sample_server_creds')
            }
            stages {
                    stage ("build") {
                                      steps {
                                              echo 'building..echo'
                                                  echo "building version ${NEW_VERSION}"
                                            }
                
                                    }
                        stage ("test") {
                                      steps {
                                              echo 'Testing..echo'
                                            }
                
                                    }

                        stage ("Dev_test") {
                                    when {
                                                expression {
                                                                        BRANCH_NAME=='dev' || BRANCH_NAME=='master'
                                                            
                                                }
                                    }
                                      steps {
                                              echo 'Testing..echo in expression'
                                            }
                
                                    }
                        
                        stage ("deploy") {
                                      steps {
                                              echo 'Deploying..echo'
                                                  echo "print credentials ${SERVER_CREDENTIALS}"

                                                  withCredentials ([
                                                              usernamePassword (credentials: 'sample_server_creds', usernameVariable: USER, passwordVariable: PWD)
                                                  ])
                                                  {
                                                              sh "some script ${USER} ${PWD}"
                                                  }
                                            }
                
                                    }
                  }
            post {
                        always {
                                    echo ' in always block'
                               }
                        success {
                                    echo ' in success block'
                               }
                        failure {
                                    echo ' in failure block'
                               }
                 }
          }
