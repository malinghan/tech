要在提交代码到 GitHub 时避免输入用户名和密码，您可以使用 SSH 协议进行身份验证，或者使用个人访问令牌（Personal Access Token）来代替密码。以下是两种方法的说明：

### 使用SSH协议

1. **配置SSH密钥**：
   确保您已经配置了 SSH 密钥，并且将公钥添加到了您的 GitHub 账户中。请参考之前的回答中提供的步骤。

2. **将远程仓库地址设置为SSH协议**：
   在本地项目目录中，执行以下命令来将远程仓库地址设置为使用 SSH 协议：
   ```
   git remote set-url origin git@github.com:username/repository.git
   ```
   将 `username` 替换为您的 GitHub 用户名，`repository` 替换为您的仓库名称。

3. **提交代码**：
   现在，当您执行 `git push` 时，Git 将会使用 SSH 密钥来进行身份验证，而不需要输入用户名和密码。

### 使用个人访问令牌（Personal Access Token）

1. **生成个人访问令牌**：
   登录到您的 GitHub 账户，然后导航到设置（Settings）页面的 Developer settings > Personal access tokens。点击生成新的令牌，选择需要的权限，并为令牌提供一个描述性的名称。

2. **将个人访问令牌用作密码**：
   在您的本地项目目录中，执行以下命令以将个人访问令牌用作密码：
   ```
   git remote set-url origin https://username:personal-access-token@github.com/username/repository.git
   ```
   将 `username` 替换为您的 GitHub 用户名，`personal-access-token` 替换为您生成的个人访问令牌，`repository` 替换为您的仓库名称。

3. **提交代码**：
   现在，当您执行 `git push` 时，Git 将使用您提供的个人访问令牌进行身份验证，而不需要输入用户名和密码。

以上两种方法都可以使您在提交代码到 GitHub 时免除输入用户名和密码的步骤。您可以根据个人偏好选择其中一种方法进行配置。