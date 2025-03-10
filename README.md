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


### Http Methods | perform using postmap
#### Post Methods to add user in dynamodb table
```
https://7akb35nnne.execute-api.us-east-2.amazonaws.com/Prod/user/pavan
```
##### add body data
```
{
    "firstName": "pavan",
    "lastName": "patel",
    "email" : "xyz@email.com",
    "website" : "aws.com"
}
```

### get Methods to get user from dynamodb table
```
https://7akb35nnne.execute-api.us-east-2.amazonaws.com/Prod/user/pavan
```

### delete Methods to delete user from dynamodb table
```
https://7akb35nnne.execute-api.us-east-2.amazonaws.com/Prod/user/pavan
```