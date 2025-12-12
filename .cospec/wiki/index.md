# HRMS 项目技术文档索引

## 📚 文档导航

本索引为AI提供HRMS项目的完整技术文档导航，支持快速信息定位和上下文理解。

### 📋 项目概述

**项目定位**: HRMS是基于Go语言开发的人力资源管理系统，采用多分公司数据隔离架构，提供完整的企业级HR管理解决方案。

**技术栈**: Go 1.23.0 + Gin 1.8.1 + GORM 1.24.2 + Layui 2.5.5，支持MySQL和SQLite双数据库。

**架构特点**: 三层架构设计（Handler-Service-Model），基于Cookie的会话管理，RBAC权限控制，分公司级数据隔离。

### 🏗️ 组织结构

hrms/
├─ main.go                     # 应用程序入口文件，初始化配置、数据库和服务
├─ go.mod & go.sum            # Go模块依赖管理文件
├─ build.sh                   # 构建脚本，支持多平台编译和数据库管理
├─ config/                    # 配置区：全局参数设置
│  ├─ config-dev.yaml         # 开发环境配置文件
│  └─ config-prod.yaml        # 生产环境配置文件
├─ handler/                   # 接口层：接收HTTP请求，关联业务：用户认证、员工管理
│  ├─ account.go              # 用户登录和认证处理
│  ├─ authority.go            # 权限管理相关处理
│  ├─ staff.go                # 员工管理相关处理
│  └─ [其它核心功能处理器文件]
├─ model/                     # 数据模型层：定义数据结构和关系
│  ├─ staff.go                # 员工数据模型定义
│  ├─ authority.go            # 权限数据模型定义
│  └─ [其它业务模型文件]
├─ service/                   # 服务层：处理业务逻辑
│  ├─ biz.go                  # 通用业务逻辑处理
│  ├─ authority.go            # 权限业务逻辑处理
│  └─ [其它业务服务文件]
├─ resource/                  # 资源配置层：数据库连接管理和全局配置
│  └─ resource.go             # 数据库连接池和多分公司数据映射管理
├─ cmd/                       # 命令行工具目录
│  ├─ migrate/                # 数据库迁移工具
│  ├─ sqlexec/                # SQL执行工具
│  └─ createdb/               # 数据库创建工具
├─ views/                     # 前端视图文件
│  ├─ index.html              # 主页面模板
│  ├─ login.html              # 登录页面模板
│  └─ admin_*.html            # 管理员页面模板
├─ static/                    # 静态资源文件
│  ├─ css/                    # 样式文件
│  ├─ js/                     # JavaScript文件
│  └─ images/                 # 图片资源
├─ sql/                       # SQL脚本目录
│  └─ sqlite_init.sql         # SQLite数据库初始化脚本
└─ data/                      # 数据存储目录

### 🎯 核心文档导航

| 文档名称 | 文件路径 | 主要内容 | 适用场景 |
|---------|---------|---------|---------|
| **项目概述** | [${workspaceFolder}/.cospec/wiki/1、项目概述.md](${workspaceFolder}/.cospec/wiki/1、项目概述.md) | 系统定位、技术栈、核心特性和功能概览 | 项目理解、技术选型、需求分析 |
| **快速入门指南** | [${workspaceFolder}/.cospec/wiki/2、快速入门指南.md](${workspaceFolder}/.cospec/wiki/2、快速入门指南.md) | 环境搭建、系统安装、配置指南和基本使用 | 新手入门、环境部署、快速上手 |
| **系统架构设计** | [${workspaceFolder}/.cospec/wiki/3、系统架构设计.md](${workspaceFolder}/.cospec/wiki/3、系统架构设计.md) | 分层架构、数据流、多数据库架构和安全设计 | 架构设计、系统分析、技术方案 |
| **核心组件详解** | [${workspaceFolder}/.cospec/wiki/4、核心组件详解.md](${workspaceFolder}/.cospec/wiki/4、核心组件详解.md) | 权限控制、用户认证、数据库连接管理等核心实现 | 深度开发、组件扩展、问题排查 |
| **功能模块实现** | [${workspaceFolder}/.cospec/wiki/5、功能模块实现.md](${workspaceFolder}/.cospec/wiki/5、功能模块实现.md) | 员工管理、考勤管理、薪资管理等业务模块实现 | 功能开发、业务逻辑理解、定制开发 |
| **前端界面设计** | [${workspaceFolder}/.cospec/wiki/6、前端界面设计.md](${workspaceFolder}/.cospec/wiki/6、前端界面设计.md) | 前端架构、页面设计规范、权限控制和数据交互 | 前端开发、UI定制、界面优化 |
| **数据库设计与管理** | [${workspaceFolder}/.cospec/wiki/7、数据库设计与管理.md](${workspaceFolder}/.cospec/wiki/7、数据库设计与管理.md) | 表结构设计、数据库迁移工具和性能优化策略 | 数据库管理、性能优化、数据迁移 |
| **开发与部署指南** | [${workspaceFolder}/.cospec/wiki/8、开发与部署指南.md](${workspaceFolder}/.cospec/wiki/8、开发与部署指南.md) | 开发环境搭建、代码规范、测试策略和部署流程 | 开发环境、代码贡献、系统部署 |
| **系统安全与权限** | [${workspaceFolder}/.cospec/wiki/9、系统安全与权限.md](${workspaceFolder}/.cospec/wiki/9、系统安全与权限.md) | 认证机制、RBAC权限设计、数据安全和威胁防护 | 安全审计、权限管理、安全加固 |
| **扩展与集成** | [${workspaceFolder}/.cospec/wiki/10、扩展与集成.md](${workspaceFolder}/.cospec/wiki/10、扩展与集成.md) | API接口设计、系统扩展机制和第三方集成方案 | 系统集成、功能扩展、二次开发 |
| **常见问题与解决方案** | [${workspaceFolder}/.cospec/wiki/11、常见问题与解决方案.md](${workspaceFolder}/.cospec/wiki/11、常见问题与解决方案.md) | 系统问题排查、错误处理和故障诊断指南 | 问题排查、运维支持、故障解决 |
| **项目总结与展望** | [${workspaceFolder}/.cospec/wiki/12、项目总结与展望.md](${workspaceFolder}/.cospec/wiki/12、项目总结与展望.md) | 技术总结、经验教训和未来发展规划 | 项目评估、技术决策、规划参考 |