# 贡献openEuler kernel社区

openEuler kernel 是 openEuler 社区维护的 Linux 内核，其源于上游 [Linux Kernel 社区](https://www.kernel.org)，并在此基础上，合入众多新特性、新硬件架构支持、性能优化、可靠性增强等补丁。本文为您提供 openEuler kernel 社区的贡献指引，欢迎您参与社区贡献，一起为 openEuler 以及下游 OS 发行版提供安全、稳定、可靠的内核基座。

## 前期准备

### 环境配置

- 注册 atomgit 账户
  openEuler kernel 项目托管在 atomgit 平台，一个正确的、合规的、有效的 atomgit 账户是参与社区贡献的前提和唯一身份标识。因此，在您参与 openEuler kernel 社区贡献前，请先注册 atomgit 账户。
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

生成 SSH 密钥：

```
ssh-keygen -t rsa -b 2048 -C "youremail\@example.com"

cat \~/.ssh/id_rsa.pub
```

登录远程仓库网站 atomgit 账户并添加密钥，在添加公钥处将上述密钥添加即可。

### 签署 CLA

在向 openEuler 提交任何贡献之前，您必须先完成 CLA 签署，只有签署了 CLA 的贡献，才能够被合入。
CLA 是 Contributor License Agreement 的缩写，即贡献者许可协议。开发者向开源项目贡献的时候通常被要求需要签署 CLA 协议，声明对贡献内容拥有所有权（或开发者得到了正确的授权进行贡献），贡献内容在项目的 License 下进行再次分发，同时保留 Copyright；如果贡献的内容包括了专利，开放这些专利给项目使用。

您可以[点击此处](https://clasign.osinfra.cn/sign/Z2l0ZWUlMkZvcGVuZXVsZXI=)查看 CLA 签署指引。

## 仓库分支关系

openEuler kernel 涉及两个仓库：

| 仓库 | 地址 | 用途 |
|------|------|------|
| 源码仓 | [openeuler/kernel](https://atomgit.com/openeuler/kernel) | 存放内核源码 |
| 制品仓 | [src-openeuler/kernel](https://atomgit.com/src-openeuler/kernel) | 保存编译打包 RPM 的 spec 脚本 |

### 源码仓分支

openEuler kernel 源码仓的分支按类型分为以下三种：

- **开发分支**：从上游 [Linux Stable](https://www.kernel.org) 对应版本检出，是社区开发的主线。新特性、bugfix、CVE 修复均合入开发分支。
- **维护分支**：从开发分支定期检出，用于维护已发布的 openEuler 发行版内核。维护分支**不直接接受新特性合入**，每周从开发分支同步 bugfix/CVE 补丁；每当新的 SP 版本发布时，会将开发分支上的新特性 rebase 同步到维护分支。维护分支的维护周期一般为两年。
- **创新分支**：每年检出一次，从开发分支或上游新内核版本检出，用于实验性特性的提前开发和验证，维护周期为半年。

> 具体生命周期详见 [openEuler 生命周期](https://www.openeuler.org/zh/other/lifecycle/)

各分支详情如下：

| 分支 | 类型 | 内核版本 | 说明 |
|------|------|----------|------|
| OLK-6.6 | 开发分支 | 6.6 | 当前主开发分支，新特性、bugfix、CVE 修复均合入此分支。从上游 Linux 6.6 Stable 检出 |
| openEuler-24.03* | 维护分支 | 6.6 | 从 OLK-6.6 检出的维护分支，每周从 OLK-6.6 同步 bugfix/CVE 补丁，新 SP 版本发布时通过 rebase 同步新特性 |
| openEuler-26.09 | 创新分支 | 6.6 | 从 OLK-6.6 检出的创新分支，用于实验性特性的开发和验证 |
| OLK-5.10 | 开发&维护分支 | 5.10 | 5.10 内核版本的开发与维护，从上游 Linux 5.10 Stable 检出 |
| openEuler-1.0-LTS | 开发&维护分支 | 4.19 | 4.19 内核版本的开发与维护，从上游 Linux 4.19 Stable 检出 |

**分支关系图：**

```
上游 Linux Stable
  │
  ├─ v6.6 ───────────────────────────────────────────────────────────
  │   │
  │   └─ OLK-6.6（开发分支）
  │       │
  │       ├── 每半年检出 ──→ openEuler-24.03*（维护分支）
  │       │                  每周同步 bugfix/CVE
  │       │                  SP 发布时 rebase 同步新特性
  │       │
  │       └── 每年检出 ────→ openEuler-26.09（创新分支）
  │                          实验性特性验证
  │
  ├─ 5.10 ─→ OLK-5.10（开发&维护分支）
  │
  └─ 4.19 ─→ openEuler-1.0-LTS（开发&维护分支）
```

> **提示**：在大多数情况下，您的补丁**只需要**提交到开发分支（如 OLK-6.6），社区会每周自动同步 bugfix/CVE 补丁到对应的维护分支，新特性则会在新 SP 版本发布时通过 rebase 同步到维护分支。

### 制品仓与源码仓分支对应

以 6.6 为例，制品仓分支与源码仓分支的对应关系如下：

| 制品仓分支 | 源码仓分支 |
|-----------|-----------|
| openEuler-24.03-LTS-Next | OLK-6.6 |
| openEuler-24.03* | openEuler-24.03* |


## 贡献规范

在参与 openEuler kernel 贡献之前，建议您先查看相关规范，符合规范的贡献将会更快得到反馈。以下是重要的规范文档索引：

- **[补丁提交规范](https://atomgit.com/openeuler/community/blob/master/sig/Kernel/%E8%A1%A5%E4%B8%81%E6%8F%90%E4%BA%A4%E8%A7%84%E8%8C%83.md)**：补丁的格式要求、提交流程、审核规则等详细说明，提交补丁前请务必阅读。
- **[特性合入规范](openEuler%20Kernel%20%E7%89%B9%E6%80%A7%E5%90%88%E5%85%A5%E8%A7%84%E8%8C%83.md)**：特性提交合入需要遵循的流程说明，包括创建"内核需求"类 issue、经 Kernel SIG 评审接纳后方可合入。

## 下载，编译和安装内核

下载，编译和安装内核，可参考以下示例：

```
git clone git@atomgit.com:openeuler/kernel.git
cd kernel
git checkout -b OLK-6.6    # 切到需要的分支
make openeuler_defconfig
make -j64
make -j64 modules_install
make install
```

## 提交贡献

### 提交 issue

在您提交贡献之前，需要先将您发现的问题或者期待改进的内容以 issue 的形式提交到 openEuler kernel 社区，便于社区 Maintainer 了解您所提补丁的具体目的。issue 类型请根据实际情况填写，可以是缺陷/BUG, 也可以是需求/特性。一个 BUG 或需求可以对应多个补丁和PR。

您可以[点击此处](https://atomgit.com/openeuler/kernel/issues)查看历史 issue 详情。

### 提交 PR

当您在本地完成代码开发后，需要以提交 PR 的形式将其贡献至 openEuler kernel 社区。
在 atomgit 中，一个 PR 由以下几个部分组成：标题、内容以及其评论、提交的代码和文件，关于 PR 提交的指引和规则已经在 openEuler 社区有完善的文档描述，您可以点击以下链接查阅：

* [提交 PR 指引](https://docs.atomgit.com/docs/start/quick)
* [如何提交一个好的 PR](https://www.openeuler.org/zh/blog/myeuler/2022-12-26-HowTosubmitPR.html)

**注意**：对于不方便直接提交 PR 的社区开发者，我们提供了补丁转 PR 的方式：您可以将修改部分的代码制作成补丁发送至 **kernel@openeuler.org** 邮件列表，成功发送后社区会自动将其转为 PR。**此外，您还可以在发送的补丁邮件中，与邮件列表里的其他社区开发者共同交流/探讨该补丁相关的技术细节和策略**。

以下内容将进一步指引您如何通过邮件发送的形式提交 PR。

#### 邮件发送

##### 准备补丁

在您提交补丁之前，请确保您的补丁可以正确地被编译且已经完成测试。

您可以通过 git-format-patch 命令生成补丁。生成补丁时，您需要注意以下事项：

* 如果您有多个版本要发送，请在补丁主题中标记“v1、v2、v3 ...”
* 请在补丁主题中准确标记您提交的目标分支。选择分支前，请参考上方[仓库分支关系](#仓库分支关系)章节了解 openEuler kernel 的分支详情
* 如果您提交的是补丁集，需要使用 --cover-letter 参数生成0号补丁，并在其中概述该补丁集做的工作
* 确保您的补丁没有编码风格问题，可以使用内核代码中的 scripts/checkpatch.pl 辅助检查

生成补丁示例：

```
git format-patch --subject-prefix="PATCH v2 OLK-6.6" -1
```

即生成一个 v2 版本的补丁，其提交的目标分支为 OLK-6.6。

##### 发送补丁

在您发送补丁到邮件列表前需要先订阅，请参考[订阅邮件列表指引](https://www.openeuler.org/zh/community/mailing-list/)：

1. [kernel@openeuler.org邮件列表](https://mailweb.openeuler.org/postorius/lists/kernel@openeuler.org/)
2. [kernel-build@openeuler.org邮件列表](https://www.openeuler.org/zh/community/mailing-list/)

使用以下命令将补丁发送到邮件列表：**kernel@openeuler.org**

```
git send-email -to="kernel@openeuler.org" --suppress-cc=all <patches>
```

**注意**：**--suppress-cc=all**是必须的，否则电子邮件将被抄送到上游社区和邮件列表中的人。

您可以[点击此处](https://git-scm.com/docs/git-send-email)查看使用 git-send-email 发送补丁程序指引。

在大多数情况下，您的补丁**只需要**发送到开发分支，每周会自动同步开发分支的 bugfix/cve 补丁到维护分支，新特性则会在新 SP 版本发布时通过 rebase 同步。您可以检出维护分支查看同步情况。

## 成为 Committer / Maintainer

openEuler Kernel SIG 的社区角色由 Contributor（贡献者）、Committer（审核者）、Maintainer（维护者）、Branch Keeper（分支守护者）四种构成。随着您对社区的持续贡献，可以申请晋升为 Committer 或 Maintainer，获得相应的代码审核与合入权限。

关于各角色的职责、权限、任免机制等详细规则，请参见 **[openEuler Kernel SIG 运作章程](https://gitcode.com/openeuler/kernel-docs/blob/master/openEuler%20Kernel%20SIG%20%E8%BF%90%E4%BD%9C%E7%AB%A0%E7%A8%8B.md)**。

### Committer 权限配置

Committer 权限的配置分为以下两步：

1. **申请 Committer 身份**（没有 Committer 身份的需要做这一步，已经是 Committer 的可直接跳过）：到 openEuler community 仓库 Kernel SIG 的 [sig-info.yaml](https://gitcode.com/openeuler/community/blob/master/sig/Kernel/sig-info.yaml) 提交 PR，将个人 atomgit id、姓名拼音、邮箱（用于 Signed-off-by）添加到 `committers:` 下方。提交 PR 后，需 Committer 信息涉及的人员评论 /lgtm，之后等待合入即可。

2. **配置 Committer 负责的模块**：到内核源码仓根目录下修改 CODEOWNERS 文件（如 OLK-6.6 的 [CODEOWNERS](https://atomgit.com/openeuler/kernel/blob/OLK-6.6/CODEOWNERS)），按照 [CODEOWNERS 规则](https://docs.atomgit.com/docs/help/home/org_project/project_manage/file_operations/code-owners/#codeowners-file)修改。修改后，可执行 `./scripts/get_codeowner.py` 验证指定模块的 Committer 配置是否符合预期。
