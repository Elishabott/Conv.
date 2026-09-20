# 需求文档

## 1. 应用概述

### 1.1 应用名称
Conveniency

### 1.2 应用描述
Conveniency 是 Dynamic 公司旗下的服务电商平台（service-commerce platform），连接客户与经过验证的专业服务人员。平台支持客户发现服务、寻找服务商、对比、预订、支付、接受服务并评价的完整流程。平台面向肯尼亚市场，未来将扩展至其他国家，需支持数百万客户与服务商。

## 2. 用户与使用场景

### 2.1 目标用户

**客户（Customer）**
- 需要专业服务的个人或企业
- 寻求可信、经过验证的服务提供者
- 希望便捷预订并安全支付

**服务提供者（Provider）**
- Conveniency Employees（员工）：通过完整入职流程的全职服务人员
- Freelancers（自由职业者）：通过注册验证流程的独立服务者

**平台管理员**
- 管理服务分类、服务商审核、订单监控、数据分析

### 2.2 核心使用场景

**客户场景**
- 搜索并发现所需服务（如家教、手机维修、平面设计、清洁、水管工、电工等）
- 浏览服务商列表，查看评分、评价、验证徽章
- 对比多个服务商
- 预订服务并通过 Stripe 完成支付
- 服务完成后进行评价

**服务提供者场景**
- 员工通道：提交申请 → 背景验证 → 技能评估 → 签约 → 培训 → 认证 → 激活 → 绩效监控
- 自由职业者通道：注册 → 身份验证 → 风险/欺诈筛查 → 设置档案 → 有限激活 → 绩效审查 → 完全激活
- 接收订单、提供服务、获得评价

## 3. 页面结构与功能说明

### 3.1 页面层级结构

```
├── Home（首页）
├── Services（服务目录）
│   └── Service Detail（服务详情）
├── Providers（服务商列表）
│   ├── Provider Detail（服务商详情）
│   └── Provider Comparison（服务商对比）
├── Academy（Dynamic Academy）
├── About（关于我们）
├── Become a Provider（成为服务提供者）
│   ├── Employee Application（员工申请）
│   └── Freelancer Registration（自由职业者注册）
├── Login（登录）
├── Register（注册）
├── Booking & Payment（预订与支付）
└── Order Management（订单管理）
```

### 3.2 页面功能说明

#### 3.2.1 Home（首页）

**导航栏**
- Logo 显示「Conveniency」
- 导航项：Home、Services、Providers、Academy、About
- 右侧：搜索图标、Login、Get Started 按钮
- 粘性导航，滚动时保持可见
- 移动端转为可折叠菜单

**Hero 区块**
- 主标题：「Find the Right Person for the Job.」
- 副标题：「Trusted services. Real professionals. Better living.」
- 说明文案：介绍 Conveniency 帮助用户找到经过验证的专业人士
- 服务搜索框：占位文本「What service do you need?」，提供示例（Tutor、Phone repair、Graphic designer、Cleaner、Plumber、Electrician）
- 主 CTA 按钮：「Find a Provider」
- 次 CTA 按钮：「Become a Provider」
- 右侧展示不对称拼贴马赛克（asymmetric mosaic）的圆角图片磁贴，包含不同专业人士图片（Technician、Tutor、Designer、Cleaner、Photographer、Electrician、Computer technician、Teacher、Business professional、Home-service worker），中央含蓝色特色卡片（Skills / Services / Community）
- 移动端响应式布局

**服务分类区块**
- 展示主要服务分类（如家政、维修、教育、设计等）
- 每个分类显示图标、名称、简短描述
- 点击分类跳转至 Services 页面对应筛选结果

**运作方式区块**
- 说明平台使用流程：发现服务 → 寻找服务商 → 对比 → 预订 → 支付 → 接受服务 → 评价
- 使用图标或插图辅助说明

**精选服务商区块**
- 展示评分高、验证完整的服务商卡片
- 每张卡片包含：服务商头像、姓名、服务类型、评分、验证徽章
- 点击卡片跳转至服务商详情页

**双轨服务模式说明区块**
- 说明两种服务提供者类型：
  + Conveniency Employees（员工）：入职流程为 Application → Background Verification → Skills Assessment → Contracting → Training → Certification → Activation → Performance Monitoring
  + Freelancers（自由职业者）：注册流程为 Registration → Identity Verification → Risk/Fraud Screening → Profile Setup → Limited Activation → Performance Review → Full Activation
- 对比两种模式的特点与优势

**数据/信任指标区块**
- 展示平台关键数据（如服务商数量、完成订单数、客户满意度等）
- 强化平台可信度

**客户评价区块**
- 展示真实客户评价
- 包含客户头像、姓名、评分、评价内容

**CTA 区块**
- 引导用户行动：「Find a Provider」或「Become a Provider」

#### 3.2.2 Services（服务目录）

**服务搜索与筛选**
- 搜索框：输入关键词搜索服务
- 分类筛选：按服务类型筛选（如家政、维修、教育、设计等）
- 排序选项：按评分、价格、距离等排序

**服务列表**
- 展示服务卡片，包含：服务名称、服务描述、价格范围、服务商数量
- 点击卡片跳转至 Service Detail 页面

**Service Detail（服务详情）**
- 服务名称、详细描述、价格范围
- 提供该服务的服务商列表
- 每个服务商显示：头像、姓名、评分、验证徽章、简短介绍
- 点击服务商跳转至 Provider Detail 页面

#### 3.2.3 Providers（服务商列表）

**服务商搜索与筛选**
- 搜索框：输入服务商姓名或服务类型
- 筛选选项：按服务类型、评分、验证状态筛选
- 排序选项：按评分、完成订单数排序

**服务商列表**
- 展示服务商卡片，包含：头像、姓名、服务类型、评分、验证徽章、简短介绍
- 点击卡片跳转至 Provider Detail 页面

**Provider Detail（服务商详情）**
- 服务商基本信息：头像、姓名、服务类型、验证徽章（员工或自由职业者）
- 评分与评价：总评分、评价数量、客户评价列表（包含评分、评价内容、评价时间）
- 服务介绍：服务商提供的服务详情、价格、可用时间
- 预订按钮：点击进入预订流程

**Provider Comparison（服务商对比）**
- 用户可选择多个服务商进行对比
- 对比维度：评分、价格、服务类型、验证状态、完成订单数
- 并排展示对比结果

#### 3.2.4 Academy（Dynamic Academy）

**培训与认证**
- 展示 Dynamic Academy 提供的培训课程
- 课程分类：技能培训、职业发展、认证课程
- 每个课程显示：课程名称、描述、时长、费用
- 点击课程查看详情或报名

**职业发展资源**
- 提供职业发展指导、行业资讯、成功案例

#### 3.2.5 About（关于我们）

**公司介绍**
- 说明 Conveniency 是 Dynamic 公司旗下产品
- 公司使命、愿景、价值观

**团队介绍**
- 展示核心团队成员（可选）

**联系方式**
- 提供联系邮箱、电话、地址

#### 3.2.6 Become a Provider（成为服务提供者）

**入口选择**
- 用户选择申请类型：Conveniency Employee（员工）或 Freelancer（自由职业者）

**Employee Application（员工申请）**
- 申请表单：填写个人信息、联系方式、服务类型、技能描述
- 提交后进入流程：Application → Background Verification → Skills Assessment → Contracting → Training → Certification → Activation → Performance Monitoring
- 显示当前流程状态

**Freelancer Registration（自由职业者注册）**
- 注册表单：填写个人信息、联系方式、服务类型、技能描述
- 提交后进入流程：Registration → Identity Verification → Risk/Fraud Screening → Profile Setup → Limited Activation → Performance Review → Full Activation
- 显示当前流程状态

#### 3.2.7 Login（登录）

- 使用 Supabase Auth 实现用户登录
- 支持邮箱密码登录
- 提供「忘记密码」功能
- 提供「注册」入口

#### 3.2.8 Register（注册）

- 使用 Supabase Auth 实现用户注册
- 注册表单：邮箱、密码、确认密码
- 注册成功后跳转至首页或用户中心

#### 3.2.9 Booking & Payment（预订与支付）

**预订流程**
- 用户选择服务商后进入预订页面
- 填写预订信息：服务日期、时间、地址、备注
- 确认预订详情：服务商信息、服务内容、价格

**支付流程**
- 使用 Stripe 支付集成（payment-stripe 技能）
- 支持信用卡/借记卡支付
- 支付成功后生成订单

#### 3.2.10 Order Management（订单管理）

**客户订单管理**
- 查看订单列表：待确认、进行中、已完成、已取消
- 订单详情：服务商信息、服务内容、预订时间、支付金额、订单状态
- 订单操作：取消订单、联系服务商、评价服务

**服务商订单管理**
- 查看接收的订单列表
- 订单详情：客户信息、服务内容、预订时间、支付金额、订单状态
- 订单操作：确认订单、完成订单、联系客户

## 4. 业务规则与逻辑

### 4.1 服务商验证与激活

**员工流程**
- 申请提交后，进入背景验证（Background Verification）
- 通过后进行技能评估（Skills Assessment）
- 评估合格后签约（Contracting）
- 完成培训（Training）并获得认证（Certification）
- 激活（Activation）后可接收订单
- 持续进行绩效监控（Performance Monitoring）

**自由职业者流程**
- 注册后进行身份验证（Identity Verification）
- 通过风险/欺诈筛查（Risk/Fraud Screening）
- 设置档案（Profile Setup）
- 有限激活（Limited Activation）后可接收少量订单
- 通过绩效审查（Performance Review）后完全激活（Full Activation）

### 4.2 预订与支付

- 客户选择服务商并填写预订信息后，进入支付流程
- 支付成功后生成订单，订单状态为「待确认」
- 服务商确认订单后，订单状态变为「进行中」
- 服务完成后，服务商标记订单为「已完成」
- 客户可对已完成订单进行评价

### 4.3 评价与评分

- 客户可对已完成订单进行评价，包含评分（1-5星）和评价内容
- 评价提交后，服务商的总评分和评价数量更新
- 评价显示在服务商详情页

### 4.4 订单取消

- 客户可在服务商确认前取消订单，支付金额原路退回
- 服务商确认后，客户取消订单需联系平台客服处理

## 5. 异常与边界情况

| 场景 | 处理方式 |
|------|----------|
| 用户未登录尝试预订 | 跳转至登录页面 |
| 支付失败 | 提示支付失败原因，允许重新支付 |
| 服务商未激活 | 不显示在服务商列表中 |
| 订单超时未确认 | 自动取消订单并退款 |
| 用户提交空评价 | 提示评价内容不能为空 |
| 服务商档案信息不完整 | 限制接单数量或不显示在列表中 |
| 搜索无结果 | 显示「未找到相关服务或服务商」 |

## 6. 数据模型

### 6.1 核心实体

**User（用户）**
- 用户ID、邮箱、密码（加密）、用户类型（客户/服务商/管理员）、注册时间

**Provider（服务商）**
- 服务商ID、用户ID、姓名、头像、服务类型、验证状态、服务商类型（员工/自由职业者）、评分、评价数量、完成订单数、激活状态、创建时间

**Service（服务）**
- 服务ID、服务名称、服务描述、服务分类、价格范围、创建时间

**Order（订单）**
- 订单ID、客户ID、服务商ID、服务ID、预订日期、预订时间、服务地址、备注、支付金额、订单状态（待确认/进行中/已完成/已取消）、创建时间

**Review（评价）**
- 评价ID、订单ID、客户ID、服务商ID、评分、评价内容、评价时间

**Application（申请）**
- 申请ID、用户ID、申请类型（员工/自由职业者）、申请状态、提交时间

### 6.2 扩展性考虑

- 数据模型需支持未来移动应用、后端微服务、AI、验证系统、Dynamic Academy、数据分析、管理后台的扩展
- 预留字段用于国家/地区扩展

## 7. 视觉与设计规范

### 7.1 设计风格

- 高端、现代、干净的科技公司美学
- 参考 SaaS 风格：宽敞布局、强排版、大视觉区、圆角卡片、平滑过渡、现代导航
- 专业、不过度花哨

### 7.2 色彩方案

- 主色调：蓝色 + 白色
- 深海军蓝：用于大标题
- 亮蓝/皇家蓝：用于主要操作按钮
- 浅蓝：用于背景和高亮
- 白色：主表面
- 极浅蓝/灰：用于次要区块
- 深中性色：用于文字

### 7.3 图片与图标

- Hero 区块使用不对称拼贴马赛克的圆角图片磁贴
- 图片展示不同专业人士（Technician、Tutor、Designer、Cleaner、Photographer、Electrician、Computer technician、Teacher、Business professional、Home-service worker）
- 使用可替换的占位图片
- 中央含蓝色特色卡片（Skills / Services / Community）

### 7.4 响应式设计

- 移动端导航转为可折叠菜单
- Hero 区块图片磁贴在移动端响应式调整布局

## 8. 技术集成

### 8.1 Supabase Auth（login 技能）

- 用于用户登录与注册
- 支持邮箱密码认证
- 管理用户会话

### 8.2 Stripe 支付（payment-stripe 技能）

- 用于订单支付
- 支持信用卡/借记卡支付
- 处理支付成功/失败回调

### 8.3 frontend-design 技能

- 确保 UI 质量符合设计规范
- 实现高端、现代的视觉效果

## 9. 非功能需求

### 9.1 可扩展性

- 平台需支持数百万客户与服务商
- 数据模型需支持未来国家/地区扩展
- 架构需支持移动应用、后端微服务、AI、验证系统、Dynamic Academy、数据分析、管理后台的扩展

### 9.2 安全性

- 用户密码加密存储
- 支付信息通过 Stripe 安全处理
- 服务商需通过背景验证或身份验证

### 9.3 语言

- 网站 UI 文案使用英文
- 面向肯尼亚市场

## 10. 验收标准

1. 用户访问首页，看到 Hero 区块（主标题「Find the Right Person for the Job.」、搜索框、CTA 按钮、图片磁贴）
2. 用户在搜索框输入服务关键词（如「Plumber」），点击「Find a Provider」，跳转至 Services 页面并显示相关服务
3. 用户点击服务卡片，进入 Service Detail 页面，查看提供该服务的服务商列表
4. 用户点击服务商卡片，进入 Provider Detail 页面，查看服务商详情（评分、评价、验证徽章）
5. 用户点击「预订」按钮，填写预订信息（日期、时间、地址），进入支付页面
6. 用户通过 Stripe 完成支付，订单生成并显示在订单管理页面
7. 服务商登录后查看订单列表，确认订单，订单状态变为「进行中」
8. 服务完成后，服务商标记订单为「已完成」，客户收到评价提示
9. 客户对订单进行评价（评分 + 评价内容），评价显示在服务商详情页
10. 用户点击「Become a Provider」，选择申请类型（员工或自由职业者），填写申请表单并提交

## 11. 本期不实现功能

- 移动应用（iOS/Android App）
- 后端微服务架构
- AI 推荐系统
- 实时聊天功能
- 地图定位与导航
- 多语言支持（仅支持英文）
- 管理后台（服务商审核、订单监控、数据分析）
- Dynamic Academy 的完整课程管理系统
- 服务商绩效监控与数据分析
- 客户与服务商的实时通知系统
- 订单争议处理与仲裁机制
- 服务商排班与日历管理
- 优惠券与促销活动
- 会员等级与积分系统