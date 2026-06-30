# AWSCDK_Bootstrap.md

AWSCDKをローカル環境で実行するには、事前に[Bootstrap]を実行する必要がある。

## Bootstrap

[AWS Management Console]に[AdministratorAccess]権限のUserでログイン
[CloudShell]を開き、以下のコマンドを実行

```
npm i -D aws-cdk
cdk --version
cdk bootstrap aws://$(aws sts get-caller-identity --query Account --output text)/ap-northeast-1
```

> 以下が表示されること

```
x.x.x (build xxxxxxx)
Bootstrapping environment aws://_account_id_/ap-northeast-1...
Trusted accounts for deployment: (none)
Trusted accounts for lookup: (none)
Using default execution policy of 'arn:aws:iam::aws:policy/AdministratorAccess'. Pass '--cloudformation-execution-policies' to customize.
CDKToolkit: creating CloudFormation changeset...
Environment aws://_account_id_/ap-northeast-1 bootstrapped.
```

## create Policy for CDK

[AWS Management Console]に[AdministratorAccess]権限のUserでログイン
[IAM] > [Policies] > 右上の[Create policy]を押下
右側の[JSON]を押下
[Policy editor]に以下を入力

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["sts:AssumeRole"],
      "Resource": ["arn:aws:iam::_account_id_:role/cdk-*"]
    }
  ]
}
```

右下の[Next]を押下

[Policy name]に以下を入力

```
CDKDeployPolicy
```

右下の[Create policy]を押下

> [Policies]画面が表示されること

[Filter by Type]で[Customer managed]を選択

> 作成した[CDKDeployPolicy]が表示されること

## create IAM user for CDK

後で[IAM user groups]を作成し、groupに権限を付与する。
[AWS Management Console]に[AdministratorAccess]権限のUserでログイン
[IAM] > [IAM users] > 右上の[Create user]を押下

[User name]に以下を入力

```
_username_
```

右下の[Next]を押下
右下の[Create user]を押下

[IAM] > [IAM users] > 上記で作成した[_username_] > [Security credentials]を押下
[Access keys] > [Create access key]を押下
[Access key best practices & alternatives]で、[Command Line Interface (CLI)]を選択
[I understand the above recommendation and want to proceed to create an access key.]にチェック
右下の[Next]を押下
[Create access key]を押下

> 作成した[Access key]を記録するか、ダウンロードすること

## create IAM user group for CDK

[AWS Management Console]に[AdministratorAccess]権限のUserでログイン
[IAM] > [IAM user groups] > 右上の[Create group]を押下

[User group name]に以下を入力

```
dev
```

[Add users to the group - Optional]で、上記で作成した[_username_]をチェック

[Attach permissions policies - Optional]で、以下をチェック

- AWSCodeCommitFullAccess
- CDKDeployPolicy

右下の[Create user group]を押下

[IAM] > [IAM user groups] > [dev] > [Permissions]を押下

> 以下の[Policies]が表示されること

```
- AWSCodeCommitFullAccess
- CDKDeployPolicy
```
