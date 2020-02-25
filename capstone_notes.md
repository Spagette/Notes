-ended on:
--putitng aws secret keys into github secrets
-up next:
--write POC lamdba source code
--do manual deploy of lambda terraform
--do a github actions deployment of lambda

TODO:
1. standup lambda terraform: https://www.terraform.io/docs/providers/aws/r/lambda_function.html
	-lambda must be put into a package
	--https://docs.aws.amazon.com/lambda/latest/dg/python-package.html

2. standup lambda github action
	-do a manual deployment to help see the process
	-figure out github actions

3. setup aws keys in github secrets
	-https://github.com/aws-actions/configure-aws-credentials -aws github action
	-https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html -manage keys
	--IAM
	---user: GitHubActions

encrypting github actions:
	https://developer.github.com/v3/actions/secrets/#example-encrypting-a-secret-using-python

Secrets API
-Get the secrets public key:
--https://api.github.com/repos/spagette/parkourmod/actions/secrets/public-key

-Get the secrets in a repo:
--https://api.github.com/repos/spagette/parkourmod/actions/secrets
