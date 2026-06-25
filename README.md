# 智能宿舍管理系统 (Smart Dormitory Management System)

## 项目简介

智能宿舍管理系统是一个基于 Spring Boot + Vue3 的现代化宿舍管理平台，旨在为高校提供智能化、便捷化的宿舍管理解决方案。

## 技术栈

### 后端技术
- **Spring Boot 3.2** - 核心框架
- **MyBatis-Plus 3.5** - ORM框架
- **Spring Security** - 安全框架
- **JWT** - 身份认证
- **MySQL 8.0** - 数据库
- **Redis** - 缓存
- **Druid** - 数据库连接池
- **Knife4j** - 接口文档

### 前端技术
- **Vue 3** - 前端框架
- **Vite** - 构建工具
- **Element Plus** - UI组件库
- **Pinia** - 状态管理
- **Vue Router** - 路由管理
- **Axios** - HTTP客户端
- **ECharts** - 图表库

## 功能模块

### 1. 首页仪表盘
- 学生总数统计
- 楼栋房间统计
- 待处理报修统计
- 能耗趋势图表
- 最新通知公告
- 最新报修工单

### 2. 宿舍楼管理
- 楼栋信息CRUD
- 楼栋类型管理（男生/女生/混合）
- 宿管员分配
- 楼栋状态管理

### 3. 房间管理
- 房间信息CRUD
- 房间类型管理（四人间/六人间/八人间/单人间）
- 床位管理
- 设施管理（独卫/空调/热水器）

### 4. 入住管理
- 学生入住办理
- 学生退宿办理
- 调宿管理
- 入住记录查询

### 5. 门禁管理
- 门禁通行记录
- 人脸识别/刷卡/密码验证
- 体温监测
- 进出统计分析

### 6. 能耗管理
- 用电量监测
- 用水量监测
- 异常用能预警
- 能耗趋势分析

### 7. 报修管理
- 在线报修提交
- 工单派发
- 维修进度跟踪
- 维修评价

### 8. 卫生检查
- 卫生检查记录
- 评分等级管理
- 违禁品检查
- 整改跟踪
- 楼栋卫生排名

### 9. 通知公告
- 通知发布
- 通知分类（系统/楼栋/宿舍/活动）
- 优先级管理
- 目标范围设置

### 10. 用户管理
- 用户信息管理
- 角色权限控制
- 账号状态管理
- 密码重置

## 项目结构

```
susheSystem/
├── src/                          # 后端源码
│   └── main/
│       ├── java/com/sushe/system/
│       │   ├── config/          # 配置类
│       │   ├── controller/      # 控制器
│       │   ├── entity/          # 实体类
│       │   ├── mapper/          # Mapper接口
│       │   ├── service/         # Service接口
│       │   │   └── impl/       # Service实现
│       │   ├── security/        # 安全相关
│       │   ├── common/          # 公共类
│       │   ├── utils/           # 工具类
│       │   ├── dto/             # 数据传输对象
│       │   └── vo/              # 视图对象
│       └── resources/
│           └── application.yml  # 配置文件
├── frontend/                     # 前端源码
│   ├── src/
│   │   ├── api/                # API接口
│   │   ├── assets/             # 静态资源
│   │   ├── components/         # 公共组件
│   │   ├── layouts/            # 布局组件
│   │   ├── router/             # 路由配置
│   │   ├── store/              # 状态管理
│   │   ├── utils/              # 工具函数
│   │   └── views/              # 页面组件
│   │       ├── dashboard/      # 首页
│   │       ├── building/       # 宿舍楼管理
│   │       ├── room/           # 房间管理
│   │       ├── checkin/        # 入住管理
│   │       ├── access/         # 门禁管理
│   │       ├── energy/         # 能耗管理
│   │       ├── repair/         # 报修管理
│   │       ├── hygiene/        # 卫生检查
│   │       ├── notice/         # 通知公告
│   │       ├── user/           # 用户管理
│   │       └── login/          # 登录页
│   ├── package.json
│   └── vite.config.js
├── sql/                          # 数据库脚本
│   └── init.sql                 # 初始化脚本
├── pom.xml                       # Maven配置
└── README.md                     # 项目说明
```

## 快速开始

### 环境要求
- JDK 17+
- Node.js 18+
- MySQL 8.0+
- Redis 6.0+

### 后端启动

1. 创建数据库并执行初始化脚本
```bash
mysql -u root -p < sql/init.sql
```

2. 修改数据库配置
编辑 `src/main/resources/application.yml`，修改数据库连接信息。

3. 启动后端服务
```bash
mvn spring-boot:run
```

后端服务将启动在 http://localhost:8080

### 前端启动

1. 安装依赖
```bash
cd frontend
npm install
```

2. 启动开发服务器
```bash
npm run dev
```

前端服务将启动在 http://localhost:3000

### 访问系统

- 前端地址：http://localhost:3000
- 后端接口：http://localhost:8080/api
- 接口文档：http://localhost:8080/api/doc.html

### 默认账号

| 角色 | 用户名 | 密码 |
|------|--------|------|
| 管理员 | admin | 123456 |
| 宿管员 | dorm_admin1 | 123456 |
| 学生 | student001 | 123456 |

## 系统截图

### 登录页面
![登录页面](docs/images/login.png)

### 首页仪表盘
![首页仪表盘](docs/images/dashboard.png)

### 宿舍楼管理
![宿舍楼管理](docs/images/building.png)

### 房间管理
![房间管理](docs/images/room.png)

## 数据库设计

### 主要数据表

| 表名 | 说明 |
|------|------|
| sys_user | 用户表 |
| dorm_building | 宿舍楼表 |
| dorm_room | 房间表 |
| dorm_bed | 床位表 |
| dorm_check_in | 入住记录表 |
| dorm_access_record | 门禁记录表 |
| dorm_energy_record | 能耗记录表 |
| dorm_repair | 报修工单表 |
| dorm_hygiene_check | 卫生检查表 |
| dorm_notice | 通知公告表 |
| sys_oper_log | 操作日志表 |

## API接口

### 认证接口
- `POST /api/auth/login` - 用户登录
- `POST /api/auth/logout` - 用户登出
- `GET /api/auth/userinfo` - 获取用户信息

### 宿舍楼接口
- `GET /api/building/page` - 分页查询
- `GET /api/building/list` - 获取列表
- `POST /api/building` - 新增
- `PUT /api/building` - 更新
- `DELETE /api/building/{id}` - 删除

### 房间接口
- `GET /api/room/page` - 分页查询
- `GET /api/room/{id}` - 获取详情
- `POST /api/room` - 新增
- `PUT /api/room` - 更新
- `DELETE /api/room/{id}` - 删除

### 入住接口
- `GET /api/checkin/page` - 分页查询
- `POST /api/checkin` - 办理入住
- `PUT /api/checkin/{id}/checkout` - 办理退宿
- `PUT /api/checkin/{id}/change-room` - 调宿

### 报修接口
- `GET /api/repair/page` - 分页查询
- `POST /api/repair` - 提交报修
- `PUT /api/repair/{id}/assign` - 派单
- `PUT /api/repair/{id}/complete` - 完成维修

### 更多接口详见接口文档

## 部署说明

### 打包后端
```bash
mvn clean package -DskipTests
```

### 打包前端
```bash
cd frontend
npm run build
```

### Docker部署（可选）
```bash
docker-compose up -d
```

## 开发团队

- 智宿未来创新团队

## 许可证

MIT License

## 联系方式

如有问题，请联系开发团队。
