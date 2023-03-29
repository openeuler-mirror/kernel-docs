# 贡献openEuler kernel社区

openEuler kernel 是 openEuler 社区维护的 Linux 内核，其源于上游 [Linux Kernel 社区](https://gitee.com/link?target=http%3A%2F%2Fwww.kernel.org)，并在此基础上，合入众多新特性、新硬件架构支持、性能优化、可靠性增强等补丁。本文为您提供 openEuler kernel 社区的贡献指引，欢迎您参与社区贡献，一起为 openEuler 以及下游 OS 发行版提供安全、稳定、可靠的内核基座。

## 前期准备

### 环境配置

- 注册 gitee 账户
  openEuler kernel 项目托管在 gitee 平台，一个正确的、合规的、有效的 gitee 账户是参与社区贡献的前提和唯一身份标识。因此，在您参与 openEuler kernel 社区贡献前，请先注册 gitee 账户。您可以[点击此处]([https://gitee.com/help]())查看gitee账户指引。
- 安装 git

1. windows 安装：[https://git-scm.com/download/win](https://git-scm.com/download/win)
2. linux 安装：不同操作系统分别对应执行以下命令

```
openEuler: dnf install git

centOS: yum install git

ubuntu: apt-get install git
```

- 配置 git

1. 全局配置用户名和邮箱

```
git config --global user.name "Your Name"

git config --global user.email <email@example.com>
```

2. 链接远程仓库

生成 SSH 密匙：

```
ssh-keygen -t rsa -C "youremail\@example.com"

cat \~/.ssh/id_rsa.pub
```

登录远程仓库网站 gitee 账户并添加密匙，在添加公钥处将上述密匙添加即可。

### 签署 CLA

在向 openEuler 提交任何贡献之前，您必须先完成 CLA 签署，只有签署了 CLA 的贡献，才能够被合入。
CLA 是Contributor License Agreement 的缩写，即贡献者许可协议。开发者向开源项目贡献的时候通常被要求需要签署 CLA 协议，声明对贡献内容拥有所有权（或开发者得到了正确的授权进行贡献），贡献内容在项目的 License 下进行再次分发，同时保留 Copyright；如果贡献的内容包括了专利，开放这些专利给项目使用。

您可以[点击此处]([https://clasign.osinfra.cn/sign/Z2l0ZWUlMkZvcGVuZXVsZXI=]())查看 CLA 签署指引。

### 贡献规范

在参与 openEuler kernel 贡献之前，建议您先查看相关规范，符合规范的贡献将会更快得到反馈。

您可以[点击此处]([https://gitee.com/openeuler/community/tree/master/sig/Kernel]())查看 openEuler kernel 规范说明。

### 下载，编译和安装内核

下载，编译和安装内核，可参考以下示例：

```
git clone git@gitee.com:openeuler/kernel.git
cd kernel
git checkout -b openEuler-1.0-LTS    # 切到需要的分支
make openeuler_defconfig
make -j64 
make -j64 modules_install
make install
```

kernel 项目有多个分支，您可以[点击此处](https://gitee.com/openeuler/community/tree/master/sig/Kernel#%E5%88%86%E6%94%AF%E7%AE%A1%E7%90%86)查看 openEuler kernel 的分支详情。

## 提交贡献

当您在本地完成代码开发后，有以下两种方式可将其提交到 openEuler kernel 社区：

* **邮件发送：**将您的修改制作成补丁并发送至邮件列表 **kernel@openeuler.org**
* **提交 PR：**将您本地的提交上传 gitee仓库以 PR 形式提交到 openEuler kernel

### 提交 issue

无论您选择哪种提交方式，在您提交之前，都需要先将您发现的问题或者期待改进的内容以 issue 的形式提交到 openEuler kernel 社区，便于社区Maintainer了解您所提补丁的具体目的。issue 类型请根据实际情况填写，可以是缺陷/Bug, 也可以是需求/特性。一个 BUG 或需求可以对应多个补丁和PR。

您可以[点击此处](https://gitee.com/openeuler/kernel/issues)查看历史 issue 详情。

### 邮件发送

#### 准备补丁

在您提交补丁之前，请确保您的补丁可以正确地被编译且已经完成测试。

您可以通过 git-format-patch 命令生成补丁。生成补丁时，您需要注意以下事项：
* 如果您有多个版本要发送，请在补丁主题中标记“v1、v2、v3 ...”
* 请在补丁主题中准确标记您提交的目标分支。选择分支前，您可以[点击此处]([https://gitee.com/openeuler/community/tree/master/sig/Kernel]([https://gitee.com/openeuler/community/tree/master/sig/Kernel]())了解 openEuler kernel 的分支详情
* 如果您提交的是补丁集，需要使用 --cover-letter 参数生成0号补丁，并在其中概述该补丁集做的工作
* 确保您的补丁没有编码风格问题，可以使用内核代码中的 scripts/checkpatch.pl 辅助检查

生成补丁示例：
```
git format-patch --subject-prefix="PATCH v2 OLK-5.10" -1
```
即生成一个 v2版本的补丁，其提交的目标分支为 OLK-5.10。

#### 发送补丁

使用以下命令将补丁发送到邮件列表：**kernel@openeuler.org**
```
git send-email *.patch -to="kernel@openeuler.org" --suppress-cc=all
```
在大多数情况下，您的补丁需要发送到开发主线，然后回合到维护分支。

例如：

1. 将补丁发送到 openEuler-1.0-LTS（OLK-4.19），然后回合到 openEuler 20.03 LTS 维护分支
2. 将补丁发送到 OLK-5.10，然后回合到 openEuler 22.03 LTS 维护分支

**说明**：OLK 为 openEuler 长期支持内核。

**注意**：如果您使用 git send-email，您必须添加 --suppress-cc=all，否则电子邮件将被抄送到上游社区和邮件列表中的人。

您可以[点击此处]([https://git-scm.com/docs/git-send-email]())查看使用 git-send-email 发送补丁程序指引。

### 提交 PR

在 gitee 中，一个 PR 由以下几个部分组成：标题、内容以及其评论、提交的代码和文件，关于 PR 提交的指引和规则已经在 openEuler 社区有完善的文档描述，您可以点击以下链接查阅：

* [提交 PR 指引]([https://gitee.com/openeuler/community/blob/master/zh/contributors/Gitee-workflow.md]())
* [如何提交一个好的 PR]([https://www.openeuler.org/zh/blog/myeuler/2022-12-26-HowTosubmitPR.html]())

