pipeline {
            agent any
            stages {
                    stage ("build") {
                                      steps {
                                              echo 'building..echo'
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
