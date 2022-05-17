# spring-gumball ci/cd example

### This example demonstrates the following two GitHub Workflows.

* https://help.github.com/actions/language-and-framework-guides/building-and-testing-java-with-gradle

* https://github.com/google-github-actions/setup-gcloud/tree/master/example-workflows/gke

### Build Dependencies

* Gradle 5.6
* JDK 11


## CI Workflow 

  - Created personal repo and added "Java CI with Gradle" in Actions
  - Changed gradle.yml file contents
![pt 1](https://user-images.githubusercontent.com/26192943/168723122-07d20ce2-c2ea-4229-9d06-8c788af60277.png)


## CD Workflow

  - Add "Build and Deploy to GKE" in Actions - unchanged
  - Change 4 tests to 2 in deployment.yaml
  - Deployment.yaml in Actions being built:
![pt2 1](https://user-images.githubusercontent.com/26192943/168735843-ab508571-b3aa-4021-9f69-22fc9da31287.png)


  - Created service account
![pt2 2](https://user-images.githubusercontent.com/26192943/168743800-0d39b55a-aeb7-47ba-831b-448c3a4e4264.png)


  - Downloaded the gold-enterprise json file
![pt2 3](https://user-images.githubusercontent.com/26192943/168743812-fe89554f-48bb-41cf-9b91-4294d3dc7500.png)



  - Added the Action Secrets using the gold-enterprise json file
![pt2 4](https://user-images.githubusercontent.com/26192943/168743824-ae2e3af3-e428-44a6-b028-d4b21706aeed.png)


  - Created Docker container
![created docker](https://user-images.githubusercontent.com/26192943/168746790-6f55ad72-1403-444a-a6ae-536aea98f6f7.png)


  - Used docker pull command but added "v2" to the command: docker pull pushpalpatil/spring-gumball:v2
![docker-pull](https://user-images.githubusercontent.com/26192943/168747061-b32d1f8f-bc83-4c67-9b1c-d0945809c7ad.png)
![docker-pull command worked](https://user-images.githubusercontent.com/26192943/168747698-2bf468c8-67f3-4e7a-afa9-2b59b499732f.png)


  - Faced an error with the ingress.yaml file because the API version in the file was not correct. Changed API version to networking.k8s.io/v1
![pt2 5 ingress error](https://user-images.githubusercontent.com/26192943/168745465-1fe4d3f7-a419-42df-9054-4679fb642162.png)
![changed APi version](https://user-images.githubusercontent.com/26192943/168745604-c8870d85-db08-45de-8c8c-c35d0e1c21bd.png)



  - Ingress successful and webpage works
![pt2 6](https://user-images.githubusercontent.com/26192943/168745499-839ec0b6-6796-433b-8b6c-cc13bb517db3.png)
![pt2 7](https://user-images.githubusercontent.com/26192943/168745630-a3991bcb-d3a4-40fb-b9af-bcd12c2106bb.png)







