# Droits

Voici les droits qui sont actuellement activés pour vos comptes IAM.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": "ec2:*",
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "aws:RequestedRegion": "eu-west-3"
                },
                "ForAllValues:StringLike": {
                    "ec2:InstanceType": [
                        "t2.micro"
                    ]
                }
            }
        }
    ]
}
```
