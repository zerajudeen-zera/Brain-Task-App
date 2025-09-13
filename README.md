assesment document with the screenshots atatched in google docs below
https://docs.google.com/document/d/10xRip9JVlSxBPtydHtsWO8rmxdRlsPhjHx4YlXAeHUo/edit?usp=sharing

# Mind task/Brain task app.

Forked the project from vennilavan to my personal github repo.
cloned into the repo and added a docker file - Dockerfile

# Dockerrized the application into an image and pushed the image to AWS ECR.

Used an EC2 ubuntu machine where i installed docker, eksctl, kubectl, aws cli and the necessary tools for the devops 

Built a CodeBuild project in AWS and conencted to my github source and mentioned the buildpsec yaml file.

Code Deploy doesnt directly support to deploy the application to kubernetes so the alternative is to use 'kubectl' in buildpsec in the code build and the the build will be deployed in the EKS using codepipeline.

built a code deploy project with the deployment group with the standard computing services.

built a code pipeline which builds the source code using github and codeBuild and then once the built is succesful it deploys using the Codedeploy configurations and Codebuild yaml file to the EKS as destination.
kubectl commands are mentioned in the buildspec.yaml files.

and finally using the service .yaml the application is hosted using a Loadbalancer and an external IP is generated.

Pushed all the yaml file in my github repo along with the source code.

i have nreplicated in 2 Nodes and it can be scaled to max amd min of 2 nodes.

since the port 3000 is not a standard port we have to explicitly mention the port followed by the DNS name.


