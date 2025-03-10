## Create A Sam Package and store in s3 bucket [pre created s3 bucket]
### it create pavan-sam.yml file with updated CodeUri
```
sam package --template-file template.yaml --output-template-file pavan-sam.yml --s3-bucket pavan-sam-tests
```

### deploy using Sam
### pass pavan-sam.yml file with region
```
sam deploy --template-file  pavan-sam.yml --stack-name pavan-sam-rest-api --region us-east-2 --capabilities CAPABILITY_IAM
```


### To check Realtime Log in console
```
sam logs -n GetUser --stack-name pavan-sam-rest-api --region us-east-2 --tail
```