# Lambda Update - GitHub Action

This action updates a Lambda function from a `.zip` file and (optionally) sends notifications about the update on Slack.

---

## Usage
1. Create a `.github/workflows/lambda-update.yml` file in your GitHub repo.
2. Add the following code to the `lambda-update.yml` file.
```yml
on: push
name: Lambda Pipeline
jobs:
  lambda-pipeline:
    name: run
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2

    - name: Updating Lambda
      uses: masoudkarimif/gh-action-lambda-update-slack@v1
      env:
        s3_bucket: <S3_BUCKET_NAME>
        s3_key: <S3_OBJECT>
        code_path: <PATH_TO_ZIP_PACKAGE>
        aws_region: <AWS_REGION>
        aws_access_key_id: <XXXXX>
        aws_secret_access_key: <XXXXX>
        slack_hook: <SLACK_HOOK_ENDPOINT>
