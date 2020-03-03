TODO:
1. standup lambda terraform: https://www.terraform.io/docs/providers/aws/r/lambda_function.html
	-lambda must be put into a package
	--https://docs.aws.amazon.com/lambda/latest/dg/python-package.html

2. standup lambda github action
	-Running command line commands in a github runner
	--use https://help.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idstepsrun
	-do a manual deployment to help see the process
	-figure out github actions

3. setup aws keys in github secrets
	-https://github.com/aws-actions/configure-aws-credentials -aws github action
	-https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html -manage keys
	--IAM
	---user: GitHubActions

---AWS---
keyid:  AKIAX3TTKWQT5FJGIZW3
key: fLKS/5OUE4yiV8u0RyiQpj1gcs9pSc+2yFUlOIho


---LAMBDA---
Lambda's with aws API Gateway:
https://docs.aws.amazon.com/lambda/latest/dg/services-apigateway.html

---GITHUB---
encrypting github actions:
	https://developer.github.com/v3/actions/secrets/#example-encrypting-a-secret-using-python

Secrets API
-Get the secrets public key:
--https://api.github.com/repos/spagette/parkourmod/actions/secrets/public-key

-Get the secrets in a repo:
--https://api.github.com/repos/spagette/parkourmod/actions/secrets


---deployment overview---
1. zip source code into zip file (lambda_src.zip)
	-in runner use: zip "zippedFileName" "file/folder to be zipped"
	-on local use: 7z a -tzip "zippedFileName" "file/folder to be zipped"
2. copy source zip to s3
	-used: aws s3 cp lambda_src.zip s3://chat-app-lambda-src/source-code/lambda_src.zip
3. terraform init
4. terraform plan -out <plan file> 
5. terraform apply <plan file>
	-plan file is used to garantee matching plan and apply(deploy)


