# Template.md

## requirements

- AWSCDK_Bootstrap.md
- Windows_Ubuntu.md
- Windows_Ubuntu_Git.md
- Windows_Ubuntu_Node.md
- Windows_Ubuntu_VSCode_RemoteDevelopment.md
- Windows_Ubuntu_AWSCLI.md

## install

### AWS CDK

Ubuntuを開き、以下のコマンドを実行

```
npm i -D aws-cdk
npx cdk --version
```

> 以下が表示されること

```
x.x.x (build xxxxxxx)
```

#### CDK init

Ubuntuを開き、以下のコマンドを実行

```
mkdir fasse_infra && cd fasse_infra
npx cdk init app --language typescript
```

> 以下が表示されること

```
✅ All done!
```
