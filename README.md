# cicd-jenkins-k8s

### Objects
    Build CICD Pipeline with jenkins, docker, k8s

### Ref
    https://www.youtube.com/watch?v=4E80gEen-o0&t=204s
    https://github.com/justmeandopensource/playjenkins
    https://www.jenkins.io/doc/book/pipeline/

### Env
    - local/test/dev

### Deploy project
Step1: Create repository for project on github  
Step2: Clone repo on devops's laptop
Step3: Setup jenkins on k8s using helm or rancher using repo bitnami
        Jenkins Blueocean Plugin
        Jenkins Kubernetes Continuous Deployment Plugin
        Jenkins Docker Plugin
Step4: Make Jenkinsfile
Step5: Run Pipeline
Step6: Enjoy result
  curl http://mywebsite.test

 

   