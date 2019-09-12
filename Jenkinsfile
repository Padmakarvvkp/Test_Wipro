node ()
{
stage ('build') {
}
stage ('test:integration-&-quality') {
}
stage ('test: functional') {
}
stage ('test: load-&-security') {
}
stage ('approval') {
  
  build stage: 'approval', wait: true
mail to: 'veeramallupadmakar@gmail.com', subject: "Please approve #${env.BUILD_NUMBER}", body: """
See ${env.BUILD_URL}input/
"""
input submitter: 'userId', message: 'Ready?'
build stage: 'deploy:prod', wait: true
}
stage ('deploy:prod') {
}
}
