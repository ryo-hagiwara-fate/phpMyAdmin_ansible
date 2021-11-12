# phpMyAdmin_ansible

- ec2構築
- s3にupload
- shell実行
```
# systems manageの設定
PARAMETER='{"ExtraVariables":["SSM=True"],"Check":["False"],"PlaybookFile":["/playbook/ec2.yml"],"SourceType":["S3"],"SourceInfo":["{\"path\":\"{{S3のURL}}\"}"],"ExtraVariables":["hostname='${RDSなどのホスト名}'"]}' && echo ${PARAMETER}

# SystemsManagerコマンド実行
aws ssm send-command --document-name "AWS-ApplyAnsiblePlaybooks" --instance-ids "${INSTANCE_ID}" --parameters ${PARAMETER} --profile ${PROFILE}
```

- その他  
  - systems manager使うとsshせずに実行可能  

- Qiitaに記事を投稿しました  
  - https://qiita.com/ryo_hagiwara/items/8409e2a0c3ef8a8769c7  
