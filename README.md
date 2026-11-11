# 基于SpringBoot+Vue的校园文件安全共享系统

![Spring Boot](https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white) ![Vue3](https://img.shields.io/badge/-Vue3-grey?style=flat-square) ![MySQL](https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white) ![MyBatis](https://img.shields.io/badge/-MyBatis-000000?style=flat-square&logo=mybatis&logoColor=white) 

## 项目介绍

本系统是一款面向高校师生与信息中心管理员的校园文件安全流转与防泄露平台，针对网盘乱传难追溯、敏感身份证号与凭证易外泄、高风险文件缺少审批、共享权限与有效期难管控、删除误操作难恢复等问题，把文件上传自动检测、目录化管理、指定用户共享、外链提取码分享、高风险复核、泄露防护策略、回收站还原与安全审计整合到同一套前后端分离工程中。

系统采用 SpringBoot + Vue 架构，区分普通用户与系统管理员：用户端完成目录管理、上传检测、定向/外链共享、预览下载与回收站处理；管理端维护检测规则与防护策略、审批高风险共享、查看即将过期共享与全校文件，并在 ECharts 看板掌握风险分布与检测趋势。高风险共享可硬性拦截并走复核，共享与外链支持过期与次数限制，适合作为毕设、课设与校园数据安全学习参考。

## 主要功能模块

- **用户认证与角色分流**：普通用户与管理员统一登录注册，JWT 鉴权；登录后按角色进入用户门户或管理看板，/admin 路由与接口双重隔离
- **网盘式目录管理**：左侧目录树新建/改名/删除，上传与列表按当前目录浏览，目录删除可连带内容进入回收站
- **上传即检**：业务文件上传后自动触发敏感内容检测，输出风险等级与评分，支持重新检测
- **我的文件中心**：按风险与共享状态筛选，支持在线预览脱敏命中、下载与删除移入回收站
- **指定用户共享**：选择接收人与预览/下载权限，可设置有效期；到期自动失效，接收方可在共享页查看
- **外链公开分享**：生成带提取码、有效期与访问次数上限的公开链接，访客无需登录即可按权限预览或下载
- **高风险共享复核**：命中高风险且开启拦截时，必须提交复核申请，管理员放行或驳回后方可共享
- **回收站**：软删除文件可还原或彻底删除，定时清理超期回收数据，降低误删风险
- **检测规则与任务**：管理端维护关键词/正则规则，查看检测任务与命中明细
- **泄露防护与审计**：配置高风险硬拦截等策略，安全审计日志记录上传、共享、下载、拦截等行为
- **经营数据看板**：文件总量、检测次数、高风险与拦截 KPI，ECharts 展示风险分布、趋势与规则命中榜
- **论文与 UML 概览**：配套论文拼图与 UML 图列表，便于答辩材料对照

## 技术架构

- **后端**：Spring Boot 2.7 + MyBatis-Plus + JWT + Lombok
- **前端**：Vue 3 + TypeScript + Vue Router + Pinia + Element Plus + Vite + ECharts
- **数据库**：MySQL 8.0

<!-- screenshots-start -->
## 系统截图

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E7%99%BB%E5%BD%95%E9%A1%B5%E9%9D%A2.png" alt="登录页面" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E7%94%A8%E6%88%B7%E9%A6%96%E9%A1%B5.png" alt="用户首页" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E6%96%87%E4%BB%B6%E5%85%B1%E4%BA%AB.png" alt="文件共享" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E6%88%91%E7%9A%84%E6%A3%80%E6%B5%8B.png" alt="我的检测" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E7%AE%A1%E7%90%86%E5%91%98%E6%95%B0%E6%8D%AE%E7%9C%8B%E6%9D%BF.png" alt="管理员数据看板" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E6%96%87%E4%BB%B6%E7%AE%A1%E7%90%86.png" alt="文件管理" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E6%A3%80%E6%B5%8B%E8%A7%84%E5%88%99.png" alt="检测规则" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E5%85%B1%E4%BA%AB%E5%A4%8D%E6%A0%B8.png" alt="共享复核" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E8%AE%BA%E6%96%87%E5%9B%BE1.png" alt="论文图1" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/%E8%AE%BA%E6%96%87%E5%9B%BE2.png" alt="论文图2" width="600" />

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/AutoUpload/screenshots/filesecurity/UML%E5%9B%BE%E5%88%97%E8%A1%A8.png" alt="UML图列表" width="600" />

<!-- screenshots-end -->

---

## 接毕业设计和论文

### 作者微信：vvsgxmn  (支持修改、 部署调试、 支持代做毕设)

### 接网站建设、小程序

### 选题+开题报告+任务书+程序定制+安装调试+论文+答辩ppt 都可以做

### 购买地址：[https://www.vvxx.love](https://www.vvxx.love)（vv毕设网）

### 支持 **一键生成 UML 图**：上传项目压缩包即可自动产出功能模块图、用例图、流程图、E-R 图、时序图等全套毕设图表。

### 提供 **免费配套软件下载 + 安装说明 + 部署教程**

![vv毕设网 - 一键画图](https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/uml-draw.png)

<img src="https://fanhua-yingcai.oss-cn-shanghai.aliyuncs.com/image-20260825133349317.png" alt="image-20260825133349317" />

⚠️ Bug添加微信**免费修复**，免费修复。其他平台的私信一律不管（微信方便发送文件）
