# ntu-ce10-2.15

To authorize an EC2 instance to retrieve secrets from AWS Secrets Manager, you need to:
- Attach an IAM role to the EC2 instance.
- Define an IAM policy that grants the necessary permissions.
- Ensure the EC2 instance assumes the IAM role when making API calls.

IAM policy that allows an EC2 instance to retrieve a specific secret:
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "secretsmanager:GetSecretValue",
      "Resource": "arn:aws:secretsmanager:ap-southeast-1:123456789012:secret:prod/cart-service/credentials"
    }
  ]
}

ARN for Secret
A sensible ARN for the secret prod/cart-service/credentials would be:
arn:aws:secretsmanager:ap-southeast-1:123456789012:secret:prod/cart-service/credentials

After that, replace ap-southeast-1 with your actual AWS region and 123456789012 with your AWS account ID.