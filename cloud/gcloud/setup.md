### Setup Cli
1. install gcloud > https://cloud.google.com/sdk/docs/downloads-interactive 
2. check profile config list 
gcloud config configurations list 

3. Create Config profile 
 - gcloud config configurations create <project>-prod-log
 - gcloud auth activate-service-account upload-prod-log@jibsoft-develop.iam.gserviceaccount.com --key-file=<file credentails json> --project=jibsoft-develop

### upload storage 

gcloud storage cp ./test.txt gs://infra-prod-log/<project folder>/ 

### set config profile

gcloud config configurations activate <project>-prod-log
