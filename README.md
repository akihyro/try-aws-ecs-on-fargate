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
    --tags Name=try-aws-ecs-on-fargate \
    --no-fail-on-empty-changeset
```
