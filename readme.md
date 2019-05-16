
# AWS API Gateway IAM Authorizer Client


This provides a simple base class for AWS API Gateway clients to
provide AWS V4 request signing for http requests when working against
APIs using IAM Authorization.


# Usage


Assuming the rest api endpoint

```python

from apigw_iam_client import Client

class MyApi(Client):

   def list_oranges(self, store_id='all'):
       return self.get("%s/oranges" % store_id).json()

```

```python
>> client = MyApi('bhttps://foix.execute-api.us-east-1.amazonaws.com/dev/')
>> client.list_oranges()
{'version': '0.1.0', 'oranges': []}

```

The client also supports obtaining credentials via STS Role Assume to
access the underlying api, by passing a role arn and optional
session_name.





