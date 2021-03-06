# jiaowuassistent

A new Flutter application.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
=======
# 北航教务小助手前端
## 使用说明

第一步，安装Android Studio和Flutter sdk，具体教程参考https://flutterchina.club/get-started/install/。

第二步，配好环境后，将项目clone到本地。

```bash
git clone git@github.com:SE2020-TopUnderstanding/BUAA-Campus-Tools-Frontend.git
```

并将文件名改成`jiaowu_assistent`。

第三步，打开Android Studio，点击`Open an existing Android Studio project`，选择下载下来的文件夹。Android Studio会自动下载Android sdk，可能需要连接VPN。

第四步，在Android Studio内安装虚拟机，编译运行项目即可。

## 错误处理

### 登录

| 错误原因                                     | 反馈                           |
| -------------------------------------------- | ------------------------------ |
| 账号或密码为空                               | 账号或密码为空，请继续输入     |
| DioErrorType.CONNECT_TIMEOUT                 | 网络请求超时                   |
| DioErrorType.RECEIVE_TIMEOUT                 | 网络请求超时                   |
| DioErrorType.SEND_TIMEOUT                    | 网络请求超时                   |
| DioErrorType.RESPONSE，http状态码为401       | 账号或密码错误                 |
| DioErrorType.RESPONSE，http状态码为402       | 您的账号被锁定，请十分钟后再试 |
| DioErrorType.RESPONSE，http状态码不是401/402 | 服务器错误                     |
| DioErrorType.CANCEL                          | 请求取消                       |
| 登录过程中的其他错误                         | 未知错误                       |

### 课表

| 错误原因                 | 反馈                                                         |
| ------------------------ | ------------------------------------------------------------ |
| http状态码为401          | 账号密码已失效，这可能是因为您修改了统一认证密码，请点击下方按钮以重新登录。 |
| 获取课表过程中的其他错误 | 网络请求出错，请稍后再试                                     |
| 获取到的数据为空         | 正在获取您的数据，请稍后再试。如果您本学期没有课程，请忽略上述提示，因为此时我们不再提供课表查询功能 |

### 课程中心

| 错误原因         | 反馈                                                         |
| ---------------- | ------------------------------------------------------------ |
| http状态码为401  | 账号密码已失效，这可能是因为您修改了统一认证密码，请点击下方按钮以重新登录。 |
| 获取到的数据为空 | 目前没有获取到您的课程信息,以下是几个可能的原因及解决办法：1. 爬虫努力爬取中，请稍后再试。2. 如果您本学期课程中心没有课程，请忽略上述提示，此时我们不再提供该功能。3. 您的课程中心没有“活跃站点”，请在学校“课程中心-我的工作空间-用户偏好”页面进行偏好设置，保证希望获取ddl的课程都属于收藏站点或活跃站点，并且活跃站点不能为空。 |

### 空教室

| 错误原因                     | 反馈     |
| ---------------------------- | -------- |
| DioErrorType.CONNECT_TIMEOUT | 连接超时 |
| DioErrorType.SEND_TIMEOUT    | 请求超时 |
| DioErrorType.RECEIVE_TIMEOUT | 响应超时 |
| DioErrorType.RESPONSE        | 出现异常 |
| DioErrorType.CANCEL          | 请求取消 |
| 获取空教室时的其他错误       | 未知错误 |

### 成绩

| 错误原因        | 反馈                                                         |
| --------------- | ------------------------------------------------------------ |
| http状态码为401 | 账号密码已失效，这可能是因为您修改了统一认证密码，请点击下方按钮以重新登录。 |

## 更新日志

#### 1.0.1

修复了选择完主页后点击确认，不会退回到上一级的bug。

#### 1.0.2

1. 使用了加密算法，更安全；
2. 有了更完善的错误处理机制。

#### 1.0.3

1. 优化了检测版本更新功能；
2. 在帮助中心添加了版本号的显示。

#### 1.0.4

成绩查询中添加夏季的成绩的查询。

#### 1.0.5

1. 课程中心DDL支持手动选择不显示”已完成“的作业项；
2. 修复了部分19级同学的DDL爬取的bug，之前因为DDL部分的bug，导致许多同学的DDL没有更新，或者新用户没有爬到DDL数据，在这里向大家致歉！
