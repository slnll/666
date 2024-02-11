# 正方教务管理系统成绩推送

<img src="https://raw.githubusercontent.com/NianBroken/ZFCheckScores/main/img/21.png" style="zoom:60%;" />

## 简介

**使用本项目前：**

早晨睡醒看一遍教务系统、上厕所看一遍教务系统、刷牙看一遍教务系统、洗脸看一遍教务系统、吃早餐看一遍教务系统、吃午饭看一遍教务系统、睡午觉前看一遍教务系统、午觉醒来看一遍教务系统、出门前看一遍教务系统、吃晚饭看一遍教务系统、洗澡看一遍教务系统、睡觉之前看一遍教务系统

**使用本项目后：**

成绩更新后**自动发通知到微信** 以节省您宝贵的时间

## 测试环境

正方教务管理系统 版本 V8.0.0

如果你的教务系统页面与下图所示的页面**完全一致**或**几乎一致**，则代表你可以使用本项目。

<img src="https://raw.githubusercontent.com/NianBroken/ZFCheckScores/main/img/26.png" style="zoom:60%;" />

## 目前支持的功能

1. 主要功能

   1. 每隔 30 分钟自动检测一次成绩是否有更新，若有更新，将通过微信推送及时通知用户。

2. 相较于教务系统增加了哪些功能？

   1. 显示成绩提交时间，即成绩何时被录入教务系统。
   2. 显示成绩提交人姓名，即成绩由谁录入进教务系统。
   3. 成绩信息按时间降序排序，确保最新的成绩始终在最上方，提升用户查阅效率。
   4. 计算 `GPA`
   5. 计算百分制 `GPA`
   6. 显示未公布成绩的课程，即已选课但尚未出成绩的课程。
   7. 显示异常的课程，即已出成绩但用户未选课的课程。

## 使用方法

### 1. [Fork](https://github.com/NianBroken/ZFCheckScores/fork "Fork") 本仓库

`Fork` → `Create fork`

### 2. [开启](https://github.com/kekeaiaixueer/ZFCheckScores/settings/actions "开启")工作流读写权限

`Settings` → `Actions` → `General` → `Workflow permissions` →`Read and write permissions` →`Save`

### 3. [添加](https://github.com/kekeaiaixueer/ZFCheckScores/settings/secrets/actions "添加") Secrets

`Settings` → `Secrets and variables` → `Actions` → `Secrets` → `Repository secrets` → `New repository secret`

> Name = Name，Secret = 例子

| Name     | 例子                       | 说明                                                                                                                 |
| -------- | -------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| URL      | https://www.nianbroken.top | 教务系统地址                                                                                                         |
| USERNAME | 2971802058                 | 教务系统用户名                                                                                                       |
| PASSWORD | Y3xhaCkb5PZ4               | 教务系统密码                                                                                                         |
| TOKEN    | J65KWMBfyDh3YPLpcvm8       | [Pushplus 的 token](https://www.pushplus.plus/doc/guide/openApi.html#_1-%E8%8E%B7%E5%8F%96token "Pushplus 的 token") |

### 4. [开启](https://github.com/kekeaiaixueer/ZFCheckScores/actions "开启") Actions

`Actions` → `I understand my workflows, go ahead and enable them` → `CheckScores` → `Enable workflow`

### 5. [运行](https://github.com/kekeaiaixueer/ZFCheckScores/actions/workflows/main.yml "运行")程序

`Actions` → `CheckScores` → `Run workflow`

_若你的程序正常运行且未报错，那么在此之后，程序将会每隔 30 分钟自动运行一次_

_若你看不懂上述使用方法，你可以查看[详细使用方法](https://github.com/NianBroken/ZFCheckScores/blob/main/DetailedUsage.md "详细使用方法")_

## 程序逻辑

1. 清空文件 B 中的内容
2. 将文件 A 中的内容写入到文件 B
3. 清空文件 A 中的内容
4. 将获取到的成绩进行 MD5 加密
5. 将加密后的成绩写入到文件 A
6. 比对文件 A 与文件 B 的内容是否一致
7. 若一致则表示成绩未更新，若不一致则表示成绩已更新

_若是第一次运行程序，上述步骤会执行两遍_

## 许可证

本项目采用 [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0 "Apache-2.0") 许可证。简而言之，你可以自由使用、修改和分享本项目的代码，但前提是在其衍生作品中必须保留原始许可证和版权信息，并且必须以相同的许可证发布所有修改过的代码。

## 特别感谢

[openschoolcn/zfn_api](https://github.com/openschoolcn/zfn_api "openschoolcn/zfn_api")

## 其他

欢迎提交 `Issues` 和 `Pull requests`
