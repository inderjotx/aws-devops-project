# aws-devops-project

## As part of this project we will create a CI/CD pipeline using AWS tools and deploy Netflix Application on EC2 Instance . 
We will use :
1. `CodeCommit` : For Source Code Management
2. `CodeBuild` : For Building and testing our code in serverless fashion
3.  `CodeDeploy` : For deploy our code
4.  `CodePipeline` : To steamline the CI/CD pipeline

---
## 1. Setting Up Source Code Repository in CodeCommit 

1. Open you aws account
2. Search For AWS CodeCommit
3. Create New Repository
   ![image](https://github.com/inderharrysingh/aws-devops-project/assets/112561014/630500c6-b519-442e-bc54-dd281c7a4fe2)
4. We will use ssh to connect to our repository, for the same we have to create a AWS User , with permission to access this repository
     1. Go to the IAM console and create a user.
     2. Click on create user
      ![image](https://github.com/inderharrysingh/aws-devops-project/assets/112561014/c4cafbcb-7a0a-49b4-9caa-bb919dc5f5b1)
     3. Add Permission for full access to code commit
      ![image](https://github.com/inderharrysingh/aws-devops-project/assets/112561014/4bcd389c-33ae-4abc-8afa-883479172b91)
     4. Click on create for user.
     5. Click on the user and go to the security credentials section
     6. Now we are going to create ssh credentials for this user
     7. Go to the terminal and run this command  
        ```
         ssh-keygen
        ```
     8. Keep all the default values
     9. Copy the public key using `cat ~/.ssh/id_rsa.pub`
     10. And paste it to the security cerentials , ssh public key for code commit section , and copy the ssh key id 
     11. Go back to the repository and copy the url for git connection
     12. ![image](https://github.com/inderharrysingh/aws-devops-project/assets/112561014/0f895930-2429-4462-9793-91ff11399bfb)
     13.  ```
          cd ~/.ssh
          touch config
          add these lines in the config file
          Host git-codecommit.*.amazonaws.com
              User <paste ssh key id that you copied earlier>
              IdentityFile ~/.ssh/id_rsa

          ```
     13. Now we can connect to this repo
     14. Run this command now
          ```
          git clone <ssh key url>
          ```

     

