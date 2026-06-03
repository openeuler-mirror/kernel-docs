## 前言

第1条：为规范 openEuler Kernel SIG 的运作，保障 openEuler 内核开发与维护活动，指导社区参与者进行开发活动，依据《openEuler项目群开源治理制度》，在openEuler 技术委员会的指导下，制定本章程。

## 第一章 愿景与使命

第2条：愿景：为世界提供数字基础设施的开源操作系统内核。

第3条：使命：通过开源、开放的社区协作，促进操作系统技术创新、成熟、与应用，为数字基础设施提供高效、安全、稳定的操作系统内核。

##  第二章 社区行为准则

第4条：社区开发活动应遵守[《openEuler社区行为准则》](https://www.openeuler.org/zh/community/conduct/)和[《openEuler社区开发行为规范》](https://atomgit.com/openeuler/community/blob/master/zh/technical-committee/governance/openEuler%E7%A4%BE%E5%8C%BA%E5%BC%80%E5%8F%91%E8%A1%8C%E4%B8%BA%E8%A7%84%E8%8C%83.md)。

## 第三章 Kernel SIG 的构成

第5条：Kernel SIG （以下简称 SIG 组）由 Maintainer、Committer、Contributor 三种角色组成。

## 第四章 角色设置

第6条：Maintainer 总体负责 SIG 的运作与管理，确定SIG的技术路线、运作方式、项目计划、版本发布、参与或组织社区活动、召集SIG组会议、决策代码合入等。Maintainer 数量一般不超过7人。

第7条：Committer 是 SIG 组的重要参与者，是内核子系统、硬件架构、驱动或子模块的维护者，负责分管领域的开发、维护、技术路线、代码审核或SIG指定的其他专项工作。Committer 根据需要设置，暂不限制总人数，但相同模块的 Committer 数量不宜超过3人。

第8条：Contributor 是社区贡献者,也可以称社区开发者，Kernel SIG 不严格区分，他们可以参与代码(PR)提交、问题解决、方案讨论、文档开发和维护、代码（PR）Review、测试等。Contributor 的代码Review意见是Maintainer和 Committer 的重要参考，但本身不参与决策活动。

## 第五章 工作与职责

### 第一节 Maintainer 的工作与职责

第9条：总体负责 SIG 的运作与管理，确定SIG的技术路线、运作方式、项目计划、版本发布、参与或组织社区活动、召集SIG组会议、决策代码合入，及参与 SIG 组重大事项的决策。

第10条：根据《[openEuler项目群选举管理条例](https://www.openeuler.org/zh/community/vote/)》规定，推举代表内核的技术委员会委员。

第11条：制定与决策 SIG 的运作机制/章程、开发/维护规范、漏洞响应规范、技术方案和技术路线等。

第12条：与 Release SIG 组密切协作，总体负责内核版本的开发与发布。

第13条：协调和指导 Committer 的工作，规划内核的版本与特性。

第14条：及时组织审核和决策 PR 的合入。

第15条：根据 SIG 会议指定，Maintainer 可以负责 SIG 的某些专项工作，如子版本、子分支的开发与维护工作，或SIG的其他专项工作。

### 第二节 Committer 的工作与职责

第16条：Committer 负责所属领域、子系统、模块的开发和维护。

第17条：负责跟踪所属领域的技术发展、特性规划、版本规划。

第18条：及时审核/处理所属模块的 PR 和 issue。

第19条：根据 SIG 安排，可以专项负责组织子版本、子分支的开发与维护。

第20条：根据 Maintainer 的提议，在 SIG 会议上汇报所属领域/子系统的工作情况和规划 。

## 第六章 工作方式

### 第一节 SIG 管理

第21条：定期召开 SIG 会议，原则上每2周开一次，如没有议题，可以顺延。议题包括：SIG 管理类、PR评审类、版本管理类、技术分享类等。

第22条：SIG 会议通常以线上方式公开举行，由 Maintainer 或SIG指定的 Committer 轮流主持。决策类议题，应至少于会前3天申报。

第23条：紧急事情，由两名 Maintainer 提议，可以临时召开 SIG 会议。

第24条：建议 Maintainer 每年在 Kernel SIG 会议上做工作报告，总结上一年工作情况，规划下一年工作计划。

第25条：SIG 会议纪要，应该会议结束一周内由会议主持人整理归档，归档位置:` kernel-docs/Kernel SIG/Meeting Record`, 归档后应当清理 [etherpad](https://etherpad.openeuler.org/p/Kernel-meetings) 上历史纪要。

### 第二节 开发活动

第26条：社区开发活动主要通过 Pull Request （以下简称PR）方式承载。

第27条：Kernel SIG 为每个活跃状态的分支设置专职的 Branch Keeper，协助 Maintainer 工作，可以由现任 Maintainer 或 Committer 兼任，根据SIG的授权，进行指定分支的管理，包括：

1. 合入经审核通过的 PR。
2. 及时处理所负责的分支 PR 和 issue，避免累积。
3. 负责版本按时发布、漏洞及时修复。
4. 确保版本满足预期目标，并满足质量要求。
5. 确保所负责的分支，代码合入符合本章程规定的原则和流程。
6. Kernel SIG 设置固定的版本管理类议题，由 Branch Keeper 汇报各分支的开发情况，包括 PR 的合入情况，版本目标或需求完成情况、是否存在问题或风险、漏洞的修复情况、issue 情况等。

第28条：Branch Keeper 由 Maintainer 自荐或在现任 Maintainer 和 Committer 中推荐，并由 SIG 会议评审通后正式担任。

第29条：PR 应满足以下条件，才允许合入：

1. 该模块的 Committer 审核通过。如该模块有多个 Committer，须没有反对意见。
2. Maintainer 没有反对意见。
3. 至少有两个（Maintainer 或 Committer ）同意的意见。
4. 如果该模块或特性没有对应 Committer，不允许合入新特性或Backport新特性。
5. 自己不能审核自己提交的 PR。

第30条：上述 PR 条件满足之后，应由 Branch Keeper 根据版本节奏，及时合入。如超过一周仍未合入，须给出合理理由。

第31条：多个 Committer 或 Maintainer 意见有分歧的，建议通过协商达成一致意见，仍然存在分歧的，可以通过 SIG 会议进行决策。

第32条：为保证 Maintainer 或 Committer 有时间进行 Review，PR 通常应该至少留有24小时的时间。需要一天之内紧急合入的 PR，除满足第30条规定的条件外，还应至少一个 Maintainer 审核同意。

第33条：已经合入社区版本的特性或模块，如果存在较多问题，且相关的 Committer 或开发者没有承担维护职责，可以经SIG会议评审，回退该特性。

第34条：如 Branch Keeper 不能胜任相关工作，或严重违反本章程规定的原则和流程，经 Maintainer 提出，SIG会议评审通过，可以取消其 Branch Keeper 资格。

第35条：Kernel SIG 仓库各角色的权限设置为：

| 角色            | 代码审核（lgtm/ack） | 代码合入(approve)                |
| :-------------- | :------------------- | :------------------------------- |
| Maintainer      | ✔️                    | ✔️[没有指定 Branch Keeper 的分支] |
| Committer       | ✔️                    | ❌                                |
| *Branch Keeper* | ❌                    | ✔️[指定分支]                      |
| Contributor     | ❌                    | ❌                                |

其他未列出的，参考[《openEuler社区SIG组成员管理方案》](https://www.openeuler.org/zh/blog/georgecao/openEuler-sig-member-management.html)。

## 第七章 决策机制

第36条：SIG 组内重大事项或争议事项，由SIG会议本着 Maintainer 集体协商一致的原则进行决策。如Maintainer 有反对意见，则议题不通过。待协商一致后，再进行会议决策。如果长时间未达成一致，可以由2名或以上Maintainer提出进行投票决策。

第37条：SIG 会议投票决策机制是：由全体与会 Maintainer 表决，如赞同票数过半，则通过。与会 Maintainer 人数需超过所有有效 Maintainer 总人数的半数是为有效会议 。

第38条：如果 Maintainer 对 SIG 决议存在争议，且经协商仍未达成一致的，可以上升到 TC 报议题。

第39条：以下事项，可以征求 SIG 组的意见，但不在 SIG 组内决策：

1. 对社区或者对其他SIG有重大影响的事项，需在 TC 报议题，申请决策。
2. KABI 兼容性清单、兼容性策略变更，需在广泛征求周边SIG组意见之后，在 TC 报议题，申请决策。

## 第八章 成员的产生与退出

### 第一节 Maintainer 的产生

第40条：现任 Maintainer 可以提名 Maintainer 候选人，经 SIG 会议评审通过，可以成为 Maintainer。

第41条：现任 Maintainer 提出不再担任时，可以同时提名一位 Maintainer 候选人继任，经 SIG 会议评审通过后，可以成为 Maintainer。被提名的候选人应满足第43条列出的条件。

第42条：为避免 Maintainer 频繁更换，如担任 Maintainer 不满足1年，则不能提名继任候选人。

第43条：Maintainer 候选人一般应具备以下条件：

1. 认可并践行 openEuler 的愿景和使命，并愿意为之努力工作。
2. 有5年以上操作系统开发经验，有意愿带领和促进 openEuler 内核的发展与繁荣，为 Kernel 的总体发展负责。
3. 能够较长期的持续参与社区开发和管理活动（至少一年），避免频繁更迭。
4. 能带领所在的组织或团队参与Kernel SIG 的开发维护工作，且所在团队有3名（含）以上 Committer。
5. 熟悉 Kernel SIG 开发和维护流程，且担任 Committer 满3个月。
6. 担任 Committer 后，累计审核超过60个PR，且累计提交补丁或解决 issue 200 个以上。

### 第二节 Maintainer 的退出

第44条：现任 Maintainer 可以向 SIG 组申请不再担任 Maintainer。

第45条：如 Maintainer 连续3个月未参与 SIG 组工作，或者不能胜任 Maintainer 的工作，经 SIG 会议决策，可以取消其 Maintainer 的资格。

### 第三节 Committer 的产生

第46条：开发者可以向 SIG 会议申报议题，申请成为某个模块或领域的 Committer。经 SIG 会议评审通过，可以成为 Committer。

第47条：满足下面条件之一，优先担任相应模块的 Committer：

1. 模块或子系统的作者，或者作者所在公司指定开发维护人员。
2. 上游社区对应模块的 Maintainer。
3. 现任或担任过 openEuler 社区其他SIG的Committer，负责 Kernel 的相关模块专项工作的。

第48条：满足下面条件，可以被提名为 Committer 候选人：

1. 致力于某个模块或者领域的开发维护工作，并在 Kernel SIG 已有较多贡献，且愿意继续担任该模块的专项开发维护工作。
2. 上述贡献包括：处理相关 issue、特性增强、上游特性/Bugfix 的 Backport、PR 审核等工作。
3. 参与 Kernel SIG 工作超过3个月。
4. 满足累计审核 PR 30个以上，且累计提交补丁或解决 issue 100 个以上。

### 第四节 Committer 的退出

第49条：现任 Committer 可以向 SIG 组申请不再担任。

第50条：SIG 会议会不定期审视 Committer 在社区参与情况。对于长期（如连续*12*个月）未参与所负责模块的开发维护活动，未履行 Committer 职责，经 SIG 会议决策通过，可以取消相关 Committer 资格。

## 第九章 附则

第51条：本文由 openEuler Kernel SIG 负责解释，并受 TC 监督和指导。

第52条：现任 Maintainer 可以提出对本章程的修改提案，经SIG会议表决通过。