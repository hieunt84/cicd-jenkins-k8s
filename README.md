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
1. Step: Create repository for project on github  
2. Step: Clone repo on devops's laptop

3. Step: Set up env k8s
4. Step: config quyền trên 02 worker node
   sudo chmod 666 /var/run/docker.sock
   sudo systemctl restart docker

NOT YET SET UP NFS SERVER

5. Step: Setup Local Registry
   chưa cần do sử dụng Docker Hub(public registry)

6. Step: Setup jenkins jenkins 2.5.4 (DEPRECATED) on k8s using helm and repo stable
    -install helm 2 or 3 ??? on devops'laptops:
      install helm 3
    -add repo stable
      helm repo add stable https://charts.helm.sh/stable

    -Config value.yaml in chart jenkins:
      helm show values stable/jenkins > jenkins.values
      vi jenkins.values

        Plugin:
          blueocean:1.18.1
          kubernetes-cd:2.0.0
          Docker pipeline not yet config

        Volumes: line 515
          not config because error

        agent:
          
        PersistentVolume:        
          not yet config
          
    -Install jenkins
      helm install -f jenkins.values jenkins stable/jenkins


7. Step: Make code for project
    index.html
    Dockerfile
    Jenkinsfile
    myweb.yaml
9. Step: Run Pipeline
10. Step6: Enjoy result
    curl http://mywebsite.test
### Note
    - Jenkins Kubernetes Continuous Deployment Plugin have error
        ref:(https://stackoverflow.com/questions/62688901/
          class-not-found-io-kubernetes-client-openapi-models-v1service)

    - research Jenkins Kubernetes Plugin
      https://www.youtube.com/watch?v=DAe2Md9sGNA&t=530s
    - research Master jenkins and slave model
