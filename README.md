# try-aws-ecs-on-fargate

AWS ECS on Fargate を試してみる。  
nginx サーバを雑に起動してみる。  

## デプロイ

デプロイする。  

```sh
aws cloudformation deploy \
    --region ap-northeast-1 \
    --template-file cfn-template.yml \
    --stack-name try-aws-ecs-on-fargate \
    --parameter-overrides VpcId=vpc-XXXXXXXX SubnetIds=subnet-XXXXXXXXXXXXXXXXX,subnet-XXXXXXXXXXXXXXXXX \
    --tags Name=try-aws-ecs-on-fargate \
    --no-fail-on-empty-changeset
```

## アンデプロイ

後始末。  

```sh
aws cloudformation delete-stack \
    --region ap-northeast-1 \
    --stack-name try-aws-ecs-on-fargate
aws cloudformation wait stack-delete-complete \
    --region ap-northeast-1 \
    --stack-name try-aws-ecs-on-fargate
```
