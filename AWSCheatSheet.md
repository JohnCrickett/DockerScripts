# Logging on to ECR and pulling an image

```bash
$(aws ecr get-login --registry-id <registry id> --no-include-email --region <region>)

docker pull <registry id>.dkr.ecr.<region>.amazonaws.com/<image>:<tag>
```
