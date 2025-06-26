# Sprint 0 - Prise en main d'AWS

* [Voici le modèle proposé par AWS](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_NAT_Instance.html)

![](<../../../../.gitbook/assets/image (23).png>)

* [Configuration du CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

{% hint style="info" %}
La région qui vous sera réservée est celle de Paris.

[AWS - Regions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html)
{% endhint %}

#### Task 01 - Obtenir la liste des vpc de la region Paris

[Doc AWS](https://docs.aws.amazon.com/cli/latest/reference/ec2/describe-vpcs.html)

![Voici le résultat à obtenir (mais via le cli)](<../../../../.gitbook/assets/image (25).png>)

```
[Request]
aws ec2 describe-vpcs --region eu-west-3


[Response]
{
    "Vpcs": [
        {
            "CidrBlock": "10.0.0.0/24",
            "DhcpOptionsId": "dopt-e979f380",
            "State": "available",
            "VpcId": "vpc-08584e8bf7e83d040",
            "OwnerId": "709024702237",
            "InstanceTenancy": "default",
            [...]
}
```

#### Task 02 Obtenir la liste des instances en modifiant le format de sortie&#x20;

Aide : [Doc AWS](https://docs.aws.amazon.com/cli/latest/reference/ec2/describe-instances.html)

```
[Request]
//TODO

[Response]
---------------------------------------------------
|                DescribeInstances                |
+----------------------+--------------------------+
|       Instance       |          Name            |
+----------------------+--------------------------+
|  i-0edd7b00f313a3908 |  Instance_Terminated     |
|  i-06fd4f875218ee29c |  Instance_Stopped        |
+----------------------+--------------------------+
```

#### Task 03 Obtenir le même type de données (task 01 et task 02) mais avec le SDK

Aide : [Doc AWS](https://aws.amazon.com/sdk-for-javascript/)
