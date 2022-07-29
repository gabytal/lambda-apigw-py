steps:

$ aws s3 mb s3://terraform-gaby-example
make_bucket: terraform-gaby-example

$ zip examplepy.zip lambda_function.py
adding: examplepy/lambda_function.py (deflated 21%)

$ aws s3 cp examplepy.zip s3://terraform-gaby-example/

$ terraform init

$ terraform apply -var="app_version=1.0.0" --auto-approve
base_url = "https://sa7lfskwkb.execute-api.us-east-1.amazonaws.com/dev/number"


We can get a reponse from the following query:

$ curl https://sa7lfskwkb.execute-api.us-east-1.amazonaws.com/dev/number?hour=10     
{"past hours": 10.0}