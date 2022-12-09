# 错误码

！！PAAS-API 错误码列表，由 `codegen -type=int -doc` 命令生成，不要对此文件做任何更改。

## 功能说明

如果返回结果中存在 `code` 字段，则表示调用 API 接口失败。例如：

```json
{
  "code": 100101,
  "message": "Database error"
}
```

上述返回中 `code` 表示错误码，`message` 表示该错误的具体信息。每个错误同时也对应一个 HTTP 状态码，比如上述错误码对应了 HTTP 状态码 500(Internal Server Error)。

## 错误码列表

PAAS-API 系统支持的错误码列表如下：

| Identifier | Code | HTTP Code | Description |
| ---------- | ---- | --------- | ----------- |
| ErrSuccess | 100001 | 200 | OK |
| ErrUnknown | 100002 | 500 | Internal server error |
| ErrBind | 100003 | 400 | Error occurred while binding the request body to the struct |
| ErrValidation | 100004 | 400 | Validation failed |
| ErrTokenInvalid | 100005 | 401 | Token invalid |
| ErrPageNotFound | 100006 | 404 | Page not found |
| ErrSetDefault | 100007 | 500 | ErrMsg=设置默认值失败 |
| ErrDatabase | 100101 | 500 | Database error |
| ErrEncrypt | 100201 | 401 | Error occurred while encrypting the user password |
| ErrSignatureInvalid | 100202 | 401 | Signature is invalid |
| ErrExpired | 100203 | 401 | Token expired |
| ErrInvalidAuthHeader | 100204 | 401 | Invalid authorization header |
| ErrMissingHeader | 100205 | 401 | The `Authorization` header was empty |
| ErrPasswordIncorrect | 100206 | 401 | Password was incorrect |
| ErrPermissionDenied | 100207 | 403 | Permission denied |
| ErrEncodingFailed | 100301 | 500 | Encoding failed due to an error with the data |
| ErrDecodingFailed | 100302 | 500 | Decoding failed due to an error with the data |
| ErrInvalidJSON | 100303 | 500 | Data is not valid JSON |
| ErrEncodingJSON | 100304 | 500 | JSON data could not be encoded |
| ErrDecodingJSON | 100305 | 500 | JSON data could not be decoded |
| ErrInvalidYaml | 100306 | 500 | Data is not valid Yaml |
| ErrEncodingYaml | 100307 | 500 | Yaml data could not be encoded |
| ErrDecodingYaml | 100308 | 500 | Yaml data could not be decoded |
| ErrGitNotConnected | 120001 | 500 | Gitea not Connected xxx |
| ErrGitTimeOut | 120002 | 500 | Gitea Connect timeout |
| ErrRepoNotFound | 120101 | 404 | Git Repo Not Found in Gitea |
| ErrPermissionDeny | 120201 | 403 | Permission Deny |
| ErrCredentials | 120202 | 401 | Error Credentials |
| ErrServiceVersionNotFound | 110001 | 404 | ServiceVersion not found |
| ErrServiceVersionAlreadyExists | 110002 | 400 | ServiceVersion Already exists |
| ErrProductDelStableVersionFirst | 110101 | 500 | Del Product Stable version Before Del Product |
| ErrProductLatestBondWithProduct | 110102 | 403 | Product-latest version not delete, bond with Product |
| ErrProductNotFound | 110103 | 404 | Product not found |
| ErrProductVersionNotFound | 110104 | 404 | Product-Version not found |
| ErrProductVersionAlreadyExists | 110105 | 400 | Product-Version Already exists |
| ErrProductAlreadyExists | 110106 | 400 | Product Already exists |
| ErrUserNotFound | 110201 | 404 | User not found |
| ErrTenantNotFound | 110301 | 404 | Tenant not found |
| ErrCommitServicesMustNotNull | 110401 | 500 | ServiceVersions Must Not Null when you commit (提测时，产品下的服务列表不能为空) |
| ErrStopBeforeDeleteInstance | 110501 | 500 | Stop the service before you perform this operation（请在操作前先停止服务） |
| ErrJobNotExists | 110502 | 500 | Job not exists（Job 配置 不存在） |
| ErrQletNotExists | 110503 | 500 | Qlet not exists（Qlet 配置 不存在） |
| ErrFaaSNotExists | 110504 | 500 | FaaS not exists（FaaS 配置 不存在） |
| ErrKubeConfFormatError | 130001 | 400 | Kubernetes Config Format Error |
| ErrPodFormatError | 130002 | 400 | Pod yaml format error |
| ErrKubePermDeny | 130101 | 400 | Secret reach the max count |

