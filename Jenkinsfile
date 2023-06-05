// #Helm_Lab


// ###################################################################################################################################################################
// #Jenkins_Lab2

// pipeline {
//     agent { label 'node' }  
    
//     stages {
//         stage('build') {
//             steps {
//                 echo 'build'
//                 script{
//                     if (BRANCH_NAME  == "release") {
//                         withCredentials([usernamePassword(credentialsId: 'credentials2', usernameVariable: 'USERNAME', passwordVariable:'PASSWORD')]) {
//                             sh '''
//                                 docker login -u ${USERNAME} -p ${PASSWORD}
//                                 docker build -t ahmedibrahimcs/bakehouse:v${BUILD_NUMBER} .
//                                 docker push ahmedibrahimcs/bakehouse:v${BUILD_NUMBER}
//                                 echo ${BUILD_NUMBER} > ../build.txt
//                             '''
//                         }
//                     }
//                     else {
//                         echo "user choosed ${BRANCH_NAME}"  
//                     }
//                 }
//             }
//         }
//         stage('deploy') {
//             steps {
//                 echo 'deploy'
//                 script {
//                     if (BRANCH_NAME  == "dev" || BRANCH_NAME == "test" || BRANCH_NAME  == "preprod") {
//                         withCredentials([file(credentialsId: 'credentials3', variable: 'KUBECONFIG')]) {
//                             sh '''
//                                 export BUILD_NUMBER=$(cat ../build.txt)
//                                 mv Deployment/deploy.yaml Deployment/deploy.yaml.tmp
//                                 cat Deployment/deploy.yaml.tmp | envsubst > Deployment/deploy.yaml
//                                 rm -f Deployment/deploy.yaml.tmp
//                                 kubectl apply -f Deployment --kubeconfig ${KUBECONFIG} -n ${BRANCH_NAME}
//                             '''
//                         }
//                     }
//                 }
//             } 
//         }  
//     }   
// }
