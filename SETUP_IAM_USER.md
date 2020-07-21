# Setup IAM User for bitrise-amazon-s3-uploader
In order to use bitrise-amazon-s3-uploader, you need to [create an IAM User](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) and [create an access key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) with this user.

Following is IAM Policy example with minimal permission for bitrise-amazon-s3-uploader to work.

```json
{
  "Statement": [
    {
      "Action": [
        "s3:PutObject",
        "s3:PutObjectAcl"
      ],
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::YOUR-BUCKET-NAME/*"
      ]
    }
  ],
  "Version": "2012-10-17"
}
```

Don't give full permission (e.g. `s3:*`) to IAM user!
